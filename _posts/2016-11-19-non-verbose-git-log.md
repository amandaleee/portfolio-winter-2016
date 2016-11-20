---
layout: post
title: Git Log, Abbreviated
---

{:.small} 
Disclaimer: All these SHAs in this post are fake. 

Last week at work I found myself in the unfortunate situation of having broken a feature, but not knowing when it happened. Usually in this situation, I use "git log". 

{% highlight bash %}
alas-macbook:my-awesome-repo home$ git log
commit 44i8wnwmj6tiac05pajp
Author: amandaleee <amandalee@amandalee.org>
Date:   Fri Nov 18 11:44:11 2016 -0500

  mobile-only markup
    
commit esc7rwjjil5lwcc2yehp
Author: amandaleee <amandalee@amandalee.org>
Date:   Fri Nov 18 10:45:23 2016 -0500
  new photo of baby, plus some markup and mobile styles

commit esc7rwjjil5lwcc2yehp
Author: amandaleee <amandalee@amandalee.org>
Date:   Fri Nov 18 10:10:13 2016 -0500
  one more color in foundation and overrides, plus markup and css for mobile first view
    
  new circle icons

{% endhighlight %}

Then I can walk back through and check out each commit, test the application, and see whether that was the commit that broke it. 

This time, however, it was going to be massively inconvenient, because I'd accidentally rebased the development branch into my feature branch before I was ready. So in addition to my commits on the feature, I would have had to walk back through about 20 additional commits. And the "git log" command returns a verbose output, particularly for commits that are actually many commits squashed into one. 

I did some StackOverflow searching and found a much less verbose way to show the log with SHAs only [no description or author]: 

git log --format=format:%H

{% highlight bash %}
alas-macbook:my-awesome-repo home$ git log --format=format:%H
a028324c2b357a8adf31
73cbe5f37c0f21fbe8ce
93451ad12d6e2ef5769f
7ab927b90ac7bcceedd3
39f9b13faf8237986204
e3f872845886c0e855b4
9827d2c18c6ae851e7b2
ecfb47986b4cebfb06b9
f53f67409b14c3a2d7ec
86c57404f58d0df4414f

{% endhighlight %}

Way less scrolling. So much more convenient! 

This led me to look into some other, less verbose ways to view the log. I found: 


%h            | abbreviated hash [seven digits only, on my machine]
%ar           | commit date
%s            | subject [the commit message]

The full docs are [https://git-scm.com/docs/pretty-formats ](here) and I'm definitely going to use this in the future. 

[And also, the feature I broke? Fixed now. Phew. ]


