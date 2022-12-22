---
cover: >-
  https://get.clevver.org/122d01bc1abc3b974c771b4eef13ae2cc7aeb1bd4b3441c02b64ea14765ae5c8.png
coverY: 0
---

# RPC Best Practices



During the Lynx Core Installer (LynxCI) execution, the program creates a lynx.conf file with default configuration settings tested and proven to work well for most installations.

When LynxCI builds the default Lynx configuration file (lynx.conf), the settings will work for most installations without further changes. The RPC username and password are dynamically generated on creation, and the RPC port is standard and doesn’t change. _The Lynx Mainnet RPC port is 9332._

The default RPC setting will also allow a connection from any external host, assuming they know your RPC username and password, so always keep them safe. Both IP4 and IP6 will be allowed to connect from any IP. This is less than ideal security, so to strengthen things, LynxCI configures the firewall to restrict access via the RPC port. As a result, RPC access is kept secure.

{% hint style="info" %}
In summary, a bad actor would need to know both your RPC username and password and have access to port 9332 on your node. By default, the node locks port 9332, so that isn’t an issue.
{% endhint %}

{% hint style="danger" %}
In some cases, you might want to allow RPC access to your node. You can first inspect your iptables firewall manually by typing ‘lyf’. This will show you port 9332 is blocked. You can then type ‘lyi’ to edit the firewall. You will see that the line for port 9332 is commented out within the file. Remove the # character at the beginning of the line, save the file, and close. Then restart the LynxCI firewall service with the command ‘sudo systemctl restart lyf’. The RPC port will now be open to the public. As long as you keep careful control of who has access to the RPC username and password, the risk of theft is low.
{% endhint %}
