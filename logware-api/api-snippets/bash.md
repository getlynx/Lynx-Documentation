---
description: >-
  The following set of Bash code snippets will allow you to craft your own
  custom shell script for your Linux CLI needs.
cover: >-
  https://get.clevver.org/814127f288e59e0148153a4c7b64be4d4d7164d321b7f0ec0b550546257bb4d1.png
coverY: -264.3884892086331
---

# Bash

_This script was built and tested on Debian 10 operating system. The script requires the following dependencies._

1. _curl_
2. _wget_
3. _jq_

## Getting Super Powers

To make things easier to manage in your bash script, let's set up some globals, as well as our debug function, at the top of the file.

{% code title="logware.sh" %}
```bash
#!/bin/bash

apiUsername="MyLogwareUsername"
apiPassword="ekkuDiJxbz6n6RKjgrwXifJFET4WMNgvbaC9"
apiEnvironment="prod" #[test|prod]
enableDebug="1" #[0|1]

function debug {
	[ "$enableDebug" = "1" ] && { echo "$1"; }
}
```
{% endcode %}

{% hint style="info" %}
&#x20;A unique API key is recommended for each use case in your application. In the event a single API key needs to be deactivated, this won't effect your other implementations.
{% endhint %}

Let's create dedicated functions for the Authentication method. This way you can check the status of the token quickly later.

```bash
function create_auth_token {
	token=$(curl -s -X POST -H 'Accept: application/json' -H 'Content-Type: application/json' --data '{"login":"'"$apiUsername"'","password":"'"$apiPassword"'"}' https://api.logware.io/api/users/authenticate | jq -r '.token')
}

function check_auth_token {
	if [ -f /tmp/$apiUsername.token ]; then #Check to see if a previously created token exists. It does exist.
		if [ "$(find /tmp/$apiUsername.token -mmin +360)" ]; then #Check to see if a previously created token is not aged out
			create_auth_token
			echo "$token" > "/tmp/$apiUsername.token" #Save the token for next time, less auth requests
			debug "Auth token had expired, recreated it."
		else
			token="$(cat /tmp/$apiUsername.token)" #use the auth token on file if not aged
			debug "Auth token has not expired. Used the one on file."
		fi
	else #A previously created token did not exist.
		create_auth_token
		echo "$token" > "/tmp/$apiUsername.token" #save the token for next time, less auth requests
		debug "Auth token didn't exist, creating one for the first time."
	fi
}
```

Now the function to make the commit request to the API. This function will allow the caller to specify which of the the Logware Methods to use. The following commit function takes the Task Id response value and looks for the Transaction Id every 2 seconds till it gets one. Once complete, the Transaction Id is returned. That step is nice, as it encapsulates some work for you.

```bash
function commit_to_api {
	# Write the data, get a TaskId from the API
	w=$(curl -s -X POST -H 'Accept: application/json' -H 'Content-Type: application/json' -H "Authorization: Bearer $token" --data '{"env":"'"$apiEnvironment"'","data":"'"$c"'"}' https://api.logware.io/api/${method})
	# Strip quotes from TaskId value
	w="${w%\"}" && w="${w#\"}"
	debug "TaskId: '$w'"
	x="null"; i=1; while [ "$x" = "null" ] ; do
		# Using the TaskId, get the TransactionId
		x=$(curl -s -H 'Accept: application/json' -H "Authorization: Bearer $token" https://api.logware.io/api/${method}/$apiEnvironment/"${w}" | jq -r '.Content[0]')
		debug "Data returned on attempt $i is '$x'"
		[ $i -gt 5 ] && { exit;}
		((i++))
		sleep 2
	done
}
```

The final code snippet is responsible for the Read and Write request options of this script.

```bash
while getopts ":m:r:w:" opt; do # only accepted values for the first argument are [hash|data|span].
  case $opt in
  	m) method="$OPTARG"
    ;;
    r) read="$OPTARG"
    ;;
    w) write="$OPTARG"
    ;;
    \?) echo "Invalid option -$OPTARG" >&2
    ;;
  esac
done

if [ -n "$read" ]; then
	# Example: ./logware.sh -r d254958cbbf634e2facc184748e2936c61bd266bea4c19d06e53be8233cabebe | base64 -d
	wget -O - -q https://chaindata.logware.io/tx/"$read" | jq -r '.pkdata'
fi

if [ -n "$write" ]; then
	# Example: ./logware.sh -w "Test" | base64 --encode
	c=$write #What data are we stashing in Logware? Param should be a string value, .ie 'this is a string'
	debug "Environment: $apiEnvironment"
	debug "Payload: $c"
	check_auth_token
	debug "API key used: '$apiUsername'"
	commit_to_api
	echo "$x" #Print the TransactionId to the screen for future retrieval.
fi
```

In the above snippet, we are are using the [_chaindata_](../public-methods/data-access-with-chaindata.md) resource to read back the data. It is very fast and doesn't tax the API with an additional call. The data pulled down from [_chaindata_](../public-methods/data-access-with-chaindata.md) is them parsed with the jq package.

{% hint style="info" %}
Don't forget to make your **logware.sh** file executable.
{% endhint %}
