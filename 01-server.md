Server
======

You can use any linux server for this, but for ease of use I
recommend a recent version of Debian. For this guide we'll be using
the free teir of Amazon's Elastic compute cloud. You can sign up
for a new account at http://aws.amazon.com/free/.

Access Keys
-----------

Make sure to note your `access key` and your `secret key`, as they
will both be needed later on in this guide.

After registering for your account, open up the EC2 control panel
to begin configuring your hosting.

    https://console.aws.amazon.com/ec2/v2/home

Amazon disables SSH password logins for security so you will need
to generate an SSH key to authorisation. Save this private key on
your local machine and be SURE to make backups as it *cannot* be
recovered later.

Security Group
--------------

EC2 machines are hosted on private networks without access to the
outside world. In order to open up ports for this server, you'll
need to create a security group. Click `Create Security Group` and
name it appropriately. Switch to the `Inbound` tab and create the
following custom rules.

    Type  Port    Source          Comment
    TCP   22      0.0.0.0/0       SSH

Instance
--------

Now to fire up your server. In the Instance section, click `Launch
Instance` and use the classic wizard. Select the `Community AMIs`
tab and punch one of the following AMIs into the search box (the
search will take about 45 seconds.)

    Zone              x86             x64
    us-east-1         ami-f494e99d    ami-9e95e8f7
    us-west-1         ami-b083aaf5    ami-9283aad7
    us-west-2         ami-a5831095    ami-4d83107d
    eu-west-1         ami-c35f43b7    ami-035f4377
    ap-southeast-1    ami-7a773e28    ami-46773e14
    ap-southeast-2    ami-7705964d    ami-7b059641
    ap-northeast-1    ami-dfde4ade    ami-b3de4ab2
    sa-east-1         ami-5e288d43    ami-26288d3b
    us-gov-west-1     ami-0992f62a    ami-0f92f62c

    Source: https://wiki.debian.org/Cloud/AmazonEC2Image/Wheezy#A7.1a

Once the image appears, click `Select` and choose your instance
type. A micro instance will do just fine for running everything but
you'll be maxed out on memory. I recommend small at minimum, medium
is great though. (Roughly $20-30/mo.)

Next we'll need to setup your new instances. Move on to [02 - Server Config](https://github.com/BitMart/howto/blob/master/02-server-config.md)
