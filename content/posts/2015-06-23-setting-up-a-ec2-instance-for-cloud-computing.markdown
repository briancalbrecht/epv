---
author: brian@briancalbrecht.com
comments: true
date: 2015-06-23 14:31:34+00:00
layout: post
link: http://www.econpointofview.com/2015/06/setting-up-a-ec2-instance-for-cloud-computing/
slug: setting-up-a-ec2-instance-for-cloud-computing
title: Setting Up a EC2 Instance for Cloud Computing
wordpress_id: 1310
categories:
- Economics
tags:
- Amazon
- AWS
- Cloud
- EC2
---

This is a little outside of my normal posts, but I think it will be helpful for some people. If not, it will simply be notes for myself.

I will show you how to get started with cloud computing. You can follow my directions with no understanding of cloud computing. However, I recommend you're become comfortable using a terminal window, using commands like "pwd" or "cd". After this, you will be able to run IPython "on the cloud." Woohoo.


# Things To Do Only Once


First you need to create an Amazon Web Services (AWS) account. Click [here](https://www.amazon.com/ap/signin?openid.assoc_handle=aws&openid.return_to=https%3A%2F%2Fsignin.aws.amazon.com%2Foauth%3Fresponse_type%3Dcode%26client_id%3Darn%253Aaws%253Aiam%253A%253A015428540659%253Auser%252Fhomepage%26redirect_uri%3Dhttps%253A%252F%252Fconsole.aws.amazon.com%252Fconsole%252Fhome%253Fstate%253DhashArgs%252523%2526isauthcode%253Dtrue%26noAuthCookie%3Dtrue&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&action=&disableCorpSignUp=&clientContext=&marketPlaceId=&poolName=&authCookies=&pageId=aws.ssop&siteState=registered%2Cen_US&accountStatusPolicy=P1&sso=&openid.pape.preferred_auth_policies=MultifactorPhysical&openid.pape.max_auth_age=120&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&server=%2Fap%2Fsignin%3Fie%3DUTF8&accountPoolAlias=&forceMobileApp=0&language=en_US&forceMobileLayout=0) and follow the instructions. Simple enough. You've done this a billion times. You will need a phone number and a credit card. Don't worry about the credit card. Everything I will show is free and I will show you how to get AWS to email you if it starts charging for some reason.[![1_signin](http://www.econpointofview.com/wp-content/uploads/2015/06/1_signin.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/1_signin.png)



After you have created an account, go to the [AWS management console](https://console.aws.amazon.com/console/home?#). In the top left of the screen, click on EC2, which stands for Elastic Cloud Compute. The "elastic" comes from the fact that you will be using some Amazon CPU when it becomes available.

[![2_ec2](http://www.econpointofview.com/wp-content/uploads/2015/06/2_ec2.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/2_ec2.png)


# Each Time You Create an Instance


Click "Launch Instance." An instance is just a virtual server that you will be using. Think of it as a virtual machine that you get to set up and customize.

[![3_launch_instance](http://www.econpointofview.com/wp-content/uploads/2015/06/3_launch_instance-1024x422.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/3_launch_instance.png)



Next you need to select the instance type. This tutorial is for Ubuntu 14.04. That is what I use, both on my local machine and on EC2. This means your virtual machine will run Ubuntu with all the Ubuntu commands.

Every tutorial I've seen is different, because Amazon keeps updating the process. Here are the steps on June 18th, 2015. Keep the "t2.micro" instance selected. It is the slowest type, but also free. Click "Next: Configure Instance Details"

[![5_step2](http://www.econpointofview.com/wp-content/uploads/2015/06/5_step2-1024x427.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/5_step2.png)



Simply click through until Step 5, where you can add tags to this instance. Tags aren't vital, but nice if you're trying to use multiple instances.

Step 6 is the important step in all of this. It is where you create a security group for the instance. Multiple instances can have the same security. In the future, you can change this, but for now, select the source to be just "My IP" on the bottom right of the screen. This only allows your local IP address to get access to your instance.

Click "Review and Launch" and then "Launch."

[![8_review](http://www.econpointofview.com/wp-content/uploads/2015/06/8_review.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/8_review.png)



**You need to download the Key Pair.** This is what allows you to use the instance. Save it on your local computer. If you lose this, you will need to copy your instance and create a new key pair. Download key pair and click launch instance.

For the key, I put it in a folder on my desktop called EC2.

Your instance is now launching. You will also get a notice about billing alerts. I recommend you set these up to make sure you don't accidentally leave a paid instance running.

[![9_billingalerts](http://www.econpointofview.com/wp-content/uploads/2015/06/9_billingalerts-1024x327.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/9_billingalerts.png)



Follow the instruction on Amazon.

After that, return to your AWS tab. Click the orange box in the top left and click on EC2 again. This will bring you to the screen that you will always use when accessing your instances.

The first time, you might see a status check on your instances saying "Initializing." Wait for that to finish.


# Every Time You Use EC2


On the left bar, under "Network & Security," click on Security groups. Then click on the security group you just created and the "Inbound" tab. This sets what is allowed to use the instance. Click Edit to allow access from the computer you're using. (I have to do this each time I use the instance. If there is a way around, let me know.)[![11_security](http://www.econpointofview.com/wp-content/uploads/2015/06/11_security-1024x516.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/11_security.png)



Again, on the left bar, click on Instances. Then click the instance you want to use, likely the only one you have. On the bottom half of the page, you should see a Public DNS. Copy the Public DNS for later use.

Now, it is finally time to get into the instance.

On your local machine, open up a Terminal Window.  Change directories to the folder that has your .pem file that you just saved.

(Note: The first time you access your instance, you will have to type "chmod 600 name_of_your.pem".

Type ssh -X -i "the name of your pem file" ubuntu@ "your public DNS that you copied"

[![11_terminal](http://www.econpointofview.com/wp-content/uploads/2015/06/11_terminal1.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/11_terminal1.png)

You are now in your very own instance. Congrats. You computing are on the cloud. Give yourself a pat on the back. That wasn't so hard.

To make sure, type "pwd" to make sure you aren't in your local directory. Type "ls" to see the instance is clear, nothing fancy going on.


# One Time: Installing Software


Well, the instance is pretty worthless now. There is nothing on it. Installing programs is simple enough. I use the list below. I use EC2 for Python (and various packages connected to Python).

    
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install xfce4
    sudo apt-get install jockey-gtk
    sudo apt-get install xdm
    sudo apt-get install ipython
    sudo apt-get install python-numpy
    sudo apt-get install python-scipy
    sudo apt-get install python-matplotlib
    sudo apt-get install python-dev
    sudo apt-get install git
    sudo apt-get install python-sphinx
    sudo apt-get install liblapack-dev
    sudo apt-get install thunar
    sudo apt-get install xfce4-terminal
    sudo apt-get install gedit              # my favorite file editor
    sudo apt-get install gitk               # to view git history
    sudo apt-get install python-sympy       # symbolic python
    sudo apt-get install imagemagick        # so you can "display plot.png"
    sudo apt-get install python-setuptools  # so easy_install is available
    sudo easy_install nose                  # unit testing framework
    sudo easy_install StarCluster           # to help manage clusters on AWS


When it asks you if you want to continue, type Y and hit Return.

Now you have a operational instance on the cloud for computing using Python. If you want to use something else, like Fortran, just search do the same thing as above, but "sudo apt-get install gfortran". This is just an Ubuntu computer where you can do everything you could do on a local Ubuntu.


# Running IPython


I use IPython and will show you how to get it running. There are two simple ways to start using IPython on your instance.

The simplest is to just type "ipython --pylab". The -- preloads IPython with the Pylab package. This opens up IPython to start playing around with. Enter "quit" to leave IPython.

[![12_ipython](http://www.econpointofview.com/wp-content/uploads/2015/06/12_ipython.png)](http://www.econpointofview.com/wp-content/uploads/2015/06/12_ipython.png)

This should pop up an image. It might take a long time. On the free instance, images are slow to load. But this should give you an understanding of how you can use EC2. It is just like a local Linux machine.

Your other option is to use the gedit package to write Python scripts. The options are endless.

To exit the EC2 Instance, simply type "exit".

I hope that convinces you that the cloud is easy and manageable, especially once you are comfortable on the command line. I'll post more about different ways that I use EC2. I learned most of what I do from a Coursera [course page](http://faculty.washington.edu/rjl/uwhpsc-coursera/index.html).

Comment below with any questions!


