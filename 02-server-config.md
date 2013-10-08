Server Config
=============

First up: SSH access. You'll need to login to your new server in 
order to configure anything. You will need the private key used to 
start your new instance (whatever.pem). If you're using windows & PuTTY,
follow [this guide](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html)
to get up and running with your new instance. Make sure to login as the `admin` user.

If you're on linux, a simple

    ssh -i whatever.pem admin@ec2-xxx-xxx-xxx-xxx.us-west-2.compute.amazonaws.com

will have you logged into your new instance in no time.

Once You're In
--------------

After logging in as the admin user, we'll need to install and configure a few packages. The first will be your web server, nginx. [Installing and configuring nginx](02.01-nginx-config.md).

After you have nginx running, you'll want to install the bitmart codebase. [Installing and configuring bitmart](02.02-bitmart-config.md).

Second, you'll need to setup tor as a relay and to point to your web server as a hidden service. [Installing and configuring tor](02.03-tor-config.md).
