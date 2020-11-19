---
title: 'How to build your Smarthome... and keep it secure'
date: 2017-06-05T08:00:08-04:00
author: Ron
layout: post
categories:
  - Uncategorized
---
![](/wp-content/uploads/2017/06/social-371650_640.png)

PC Magazine has an article [How to Build Your Smarthome: A Beginner's Guide](https://t.co/qzesSXvJbX#smarthome), describing the various components of a Smarthome. It starts by describing various protocols used to make the components of a Smarthome talk to each other, then touches on the hubs, cameras, controllers, thermostats, lighting, security, and even sprinkler controls.

It's a great start into the home automation field. However, one aspect of the Smarthome, and particularly the Internet of Things (IoT), is the network security. Most devices used in a Smarthome setup have minimal security features, and it's rare that any of them get an update after they leave the factory. This makes them the prime target for an attack on your home network.

To keep your regular, PC-and-laptop based, network separate from the insecure IoT network, requires a bit of network knowledge. Steve Gibson of GRC.com has been experimenting with various setups, evaluating each one of them, and has come to the conclusion that the best set up is as follows:

1. Obtain 3 routers. They don't have to be high-end smart routers, but they have to be routers, not switches.
2. Put one router behind your internet connection (DSL modem, Cable modem, whatever). This will allow NAT translation between the Internet and your home Intranet. We'll call this router the Master Router.
3. Put the other two routers behind the Master Router. You now create two separate networks inside your home Intranet. Let's call them Network1 and Network2.
4. Network1 machines cannot talk directly to Network2 machines, and vice versa. So now you can put your insecure IoT devices in Network2, and keep your (more) secure laptops, PCs etc. in Network1
5. If you need more segregation, you can set up a Network3, Network4, etc., depending on how many routers you have, and how many ports are available on your Master Router.

![Network Diagram](/wp-content/uploads/2016/04/Network_Diagram.png)

An important thing to remember during the setup is that they have to be acting as routers. Even after configuring them as much as possible as routers, you still have to make sure they act as NAT routers. The trick for this is to set each network up with their own network address. So the Master Router can have an internal network of 192.168.0.xxx, Network1 will be 192.168.1.xxx, Network2 will be 192.168.2.xxx, etc. etc. Each router will have the .1 address assigned, and use DHCP to get its address assigned on the WAN port. It will have DHCP enabled for its network, assigning addresses in its network as required.

PC Perspective has a [longer write-up](https://www.pcper.com/reviews/General-Tech/Steve-Gibsons-Three-Router-Solution-IOT-Insecurity) about the "Three Router Solution", including the thought process leading to the three router solution.

An alternative would be to use a router at the 192.168.0.x network, that will allow you to segment that network in subnetworks. This splits a network (like the 192.168.0.x network) up in smaller subnets, each with separate routing. A cheap but powerful solution for this would be the [Ubiquiti EdgeRouter X](https://amzn.to/2rMVD1O).

Either one of these solutions is a bit more involved than just plugging everything in one router, but it will greatly enhance your network's resistance against misbehaving IoT devices.