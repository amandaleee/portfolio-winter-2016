---
layout: post
title: Name Your Terminal Tabs for Easier Workflow
---

In my day job, at any given time, I probably have six or seven iTerm tabs open. Here's what I'm doing:
* A Grunt build
* A tab for git tasks
* A tab for my VM, where I run Gradle builds and grep
* Three tabs for the three local servers that the application runs on [these are in the VM as well]
* A tab for my personal work, which I peck at whenever I have to restart the VM or rebuild the app. 

A coworker sent me the following bash script for renaming my iTerm tabs, and it's made an enormous difference. 

{% highlight bash %}
alas-macbook:my-awesome-repo home$ PROMPT_COMMAND='echo -ne "\033]0;THE TERMINAL TAB NAME GOES HERE\007"'
{% endhighlight %}

I no longer have to type "pwd" a hundred times a day!


