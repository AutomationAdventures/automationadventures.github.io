---
id: 30
title: Integrating RequestTracker and flow.io
date: 2012-01-19T08:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=30
permalink: /2012/01/integrating-requesttracker-and-flow-io.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2012/01/integrating-requesttracker-and-flowio.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1360464584044228345
image: /wp-content/uploads/2012/01/holding-hands-500-500x372.jpg
categories:
  - agile
  - Features
  - flow.io
  - kanban
  - Perl
  - programming
  - RequestTracker
  - RT
  - Software
---
![Image by www.flickr.com/photos/petitshoo](/wp-content/uploads/2012/01/holding-hands-500.jpg)

For a year or 2 we have been using [flow.io](http://flow.io/) at the company I work at to track projects. About a year ago, we decided to use RequestTracker (RT) to track incoming helpdesk requests, and started incorporating tasks within projects. RT almost replaced flow.io, but it lacks in the visualization of the Kanban process. Rather than building a completely new Kanban board on top of RT, I decided to use flow.io as the visualization tool, and get some measurements thrown in as a bonus.

flow.io has a nice REST API interface, allowing you to get a lot of information about your boards, and create or update new tasks. Deleting tasks is done by updating a task to a status of Deleted, giving you the opportunity to undelete the task. I've worked with REST interfaces before, so I wasn't expecting a whole lot of problems there.

The challenge was RT. RT is written in Perl, and uses something called Scrips to run little scripts when something changes on an RT ticket. Scrips are pieces of Perl code. And I've never done anything in Perl before... except for a few Mister House scripts.

Below are the steps I took to make this work. It is a work in progress, and I've put it on [github](https://ronaldb@github.com/ronaldb/RT-to-flow.io.git) as an Open Source project, so feel free to improve it, fork it, or whatever.

## 1. Set up flow.io to accept REST requests

![](/wp-content/uploads/2012/01/flowio-authentication.jpg)

To accept REST requests, the flow.io API requires an authentication key. One key is already defined for you, but since flow.io unfortunately doesn't seem to use the https protocol, I suggest not to use that key, but generate a secondary key for these requests. That allows you to delete the key if needed, and generate a new key.

Generating a key is done by going to the console on your flow.io site. It's either a direct menu option, or go to your account and click on console.

## 2. Set up a Custom Field in RT

![](/wp-content/uploads/2012/01/RT-Customfield.jpg)

The custom field in RT will be used to store the flow.io ID number, so that you can update the right flow.io card when the RT ticket changes.

This field is also used later on to make sure we do not try to update flow.io cards that do not exist - if the flow.io ID number is blank, we do not have a flow.io card at all.

## 3. Select your queues that you want to expose to flow.io

![](/wp-content/uploads/2012/01/RT-queues.jpg)

You need to add the custom field to the queues that you want to use it in.

Not all queues lend itself to the Kanban board. If you have RT tickets with sensitive information in the subject line, I suggest not to put those on a board...

## 4. Create scrip

Once you have selected your queues, you need to define a Scrip that allows you to create flow.io cards. The On Create scrip in RT is triggered when a new RT ticket is created.

### 4.1 Condition

There is no condition. Maybe we should check for an existing Flow-id, but we're assuming this is a new ticket. So the condition should always return 'true' to RT:  
```
return 1;
```

### 4.2 Action

For the action part of the scrip, see the [github](https://ronaldb@github.com/ronaldb/RT-to-flow.io.git) site.

## 5. Modify scrip

Now that we have an RT ticket with a reference to the flow.io card, we need to make sure that modifications on RT are reflected on flow.io. This is done with the On Transaction scrip, which is triggered on every change made to a ticket.

### 5.1 Condition

For the condition, we only want to update RT tickets that have a flow.io ID:  
```
return 0 unless ($self->TicketObj->FirstCustomFieldValue('FlowIO-id') != "");
return 1;
```

### 5.2 Action

For the action part of the scrip, see the [github](https://ronaldb@github.com/ronaldb/RT-to-flow.io.git) site.

## 6. Initial setup

For the initial setup, I went for a manual approach. We had not that many tickets open, and it was probably faster to do this by hand, than figuring out how to do this automatically.

I now regret that choice, since there are some synchronization issues:

  * When someone enters a ticket, and immediately changes it to done, this is not detected. A flow.io card is created, and remains in the Backlog column until we fix it.
  * When the flow.io webservice is unreachable, RT still thinks everything went fine. And I probably want to keep it that way: RT is leading, flow.io is a representation of RT - to the best of our abilities.

## 7. Improvements

  * What happens when tickets move from one queue to another?
  * <del>Merging tickets</del>
  * Filter certain types of tickets
  * Take the settings out of code and put them in a config file
  * Turn the scrips into custom actions in external Perl files