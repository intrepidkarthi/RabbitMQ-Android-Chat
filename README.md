RabbitMQ-Android-Chat
=====================

RabbitMQ-Android-Chat

I spent more than 12 hours in setting up RabbitMQ server in Ubuntu and creating an Android app which communicates from server and also communicates with other devices through the server. So I thought it will be good to share the whole information I found in a single place. I found information from various sources.

http://simonwdixon.wordpress.com/2011/06/03/getting-started-with-rabbitmq-on-android-part-1/

http://kamrana.wordpress.com/2012/05/10/android-chat-application-using-rabbitmq/

http://www.danielscottlawrence.com/using-rabbitmq-management-plugin-on-ubuntu-12-04/

And as usual from http://www.stackoverflow.com

I am using Ubuntu 12.04. This tutorial is completely based on this. So I am not sure how will it work on Windows or Mac OS.

A. Install the latest version of RabbitMQ as per the instruction from here

Add the following line to your /etc/apt/sources.list:
deb http://www.rabbitmq.com/debian/ testing main
(Please note that the word testing in this line refers to the state of our release of RabbitMQ, not any particular Debian distribution. You can use it with Debian stable, testing or unstable, as well as with Ubuntu. We describe the release as “testing” to emphasise that we release somewhat frequently.)

(optional) To avoid warnings about unsigned packages, add our public key to your trusted key list using apt-key(8):
wget http://www.rabbitmq.com/rabbitmq-signing-key-public.asc
sudo apt-key add rabbitmq-signing-key-public.asc
Run apt-get update.
Install packages as usual; for instance,
sudo apt-get install rabbitmq-server
B. It is better to have a GUI client. It comes along with the installation. We just need to enable it. To enable the plugin follow the steps given below.

Install rabbitmq-server

$ sudo apt-get install rabbitmq-server

Enable the rabbitmq-management plugin

$ sudo /usr/lib/rabbitmq/lib/rabbitmq_server-2.7.1/sbin/rabbitmq-plugins enable rabbitmq_management
The following plugins have been enabled:
mochiweb
webmachine
rabbitmq_mochiweb
amqp_client
rabbitmq_management_agent
rabbitmq_management

Plugin configuration has changed. Restart RabbitMQ for changes to take effect.
Restart rabbitmq-server for the changes to take affect.

$ sudo service rabbitmq-server restart
Restarting rabbitmq-server: SUCCESS
rabbitmq-server.
Checked the newly enabled plugins

$ sudo /usr/lib/rabbitmq/lib/rabbitmq_server-2.7.1/sbin/rabbitmq-plugins list
[e] amqp_client 0.0.0
[ ] eldap 0.0.0-git
[ ] erlando 0.0.0
[e] mochiweb 1.3-rmq0.0.0-git
[ ] rabbitmq_auth_backend_ldap 0.0.0
[ ] rabbitmq_auth_mechanism_ssl 0.0.0
[ ] rabbitmq_consistent_hash_exchange 0.0.0
[ ] rabbitmq_federation 0.0.0
[ ] rabbitmq_jsonrpc 0.0.0
[ ] rabbitmq_jsonrpc_channel 0.0.0
[ ] rabbitmq_jsonrpc_channel_examples 0.0.0
[E] rabbitmq_management 0.0.0
[e] rabbitmq_management_agent 0.0.0
[ ] rabbitmq_management_visualiser 0.0.0
[e] rabbitmq_mochiweb 0.0.0
[ ] rabbitmq_shovel 0.0.0
[ ] rabbitmq_shovel_management 0.0.0
[ ] rabbitmq_stomp 0.0.0
[ ] rabbitmq_tracing 0.0.0
[ ] rfc4627_jsonrpc 0.0.0-git
[e] webmachine 1.7.0-rmq0.0.0-hg
I could new access the mangement plugin via:

http://192.168.1.2:55672/#/

Username: guest
Password: guest
If 192.168.1.2 doesn’t work try 192.168.1.*

run the app after this :)
