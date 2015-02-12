---
layout: post
title: "Manage a Racket Web Server"
description: "Process supervision and monitoring of a Racket Web Server with daemontools."
keywords: "racket, process supervisor, process supervision, daemontools, trycode.io"
date: 2015-02-11 16:35:34
permalink: manage-a-racket-web-server
published: false
categories:
  - Racket
  - monitoring
  - process supervision
  - daemontools
---
Now that my Racket Web Application is up, how do I manage it?

I don't expect the Racket Web Server to go down regularly, but I don't want to be disturbed:

###If My App Takes a Dive Into Shiz Creek

I want it to restart, and continue like nothing happened.

I need something that will supervise or monitor the Racket web server process, and restart the service if it goes down. A process supervisor.

Fortunately, there are some <a href="http://en.wikipedia.org/wiki/Process_supervision" target="_blank">process supervision</a> tools available: <a href="http://supervisord.org/" target="_blank">supervisord</a>, <a href="http://mmonit.com/monit/" target="_blank">monit</a>, <a href="http://cr.yp.to/daemontools.html" target="_blank">daemontools</a>, <a href="http://untroubled.org/daemontools-encore/" target="_blank">daemontools-encore</a>, <a href="https://github.com/bluepill-rb/bluepill" target+"_blank">bluepill</a>, <a href="http://b0llix.net/perp/" target="_blank">perp</a>, <a href="http://smarden.org/runit/" target="_blank">runit</a>, <a href="http://godrb.com/" target+"_blank">god</a>, <a href="https://github.com/kostya/eye" target="_blank">eye</a>, and <a href="http://skarnet.org/software/s6/" target="_blank">s6</a>; to name a few. I only need one.

###A Lean, Mean Process Machine
D. J. Bernstein's <a href="http://cr.yp.to/daemontools.html" target="_blank">daemontools</a> appears all but forgotten to those who choose their applications based on tweets, trends, stars and forks - which is unfortunate, as its got the thousand-yard stare and stoicism of a battle-hardened process monitoring and ass-kicking veteran.

I went with daemontools because its stable and proven, doesn't require me to install a new language or language tools, and includes logging.

####Installing and Configuring daemontools
Installing daemontools on Ubuntu is as simple as:
{% highlight bash %}
apt-get install daemontools csh daemontools-run
{% endhighlight %}

Configuring it took a little more work.

First, we need to create the following directories:

{% highlight bash %}
# create /etc/service
# /etc/service/trycode.io
# /etc/service/trycode.io/log
# in one fell swoop
mkdir -p /etc/service/trycode.io/log
{% endhighlight %}

Then we need to write the scripts that daemontools needs to run and log the service. My Racket web app sits in `/srv/trycode.io`, so I'll write the script `/srv/trycode.io/run`

{% highlight bash %}
#!/bin/sh

ID=`command -v setuidgid`
RACKET=`command -v racket`

exec $ID trycode $RACKET /srv/trycode.io/trycode/main.rkt
{% endhighlight %}

Create a log directory: `mkdir /srv/trycode.io/log`, then create shell script `/srv/trycode.io/log/run`:
{% highlight bash %}
#!/bin/sh

ID=`command -v setuidgid`
MLOG=`command -v multilog`

exec 2>&1
exec $ID trycode $MLOG t s10485760 n5 '!tai64nlocal' /var/log/trycode
{% endhighlight %}

Make both scripts executable:
{% highlight bash %}
chmod a+x /srv/trycode.io/run
chmod a+x /srv/trycode.io/log/run
{% endhighlight %}

The directory structure should now look like this:

Now create symbolic links to the scripts:
{% highlight bash %}
ln -s /srv/trycode.io/run /etc/service/trycode.io/run
ln -s /srv/trycode.io/log/run /etc/service/trycode.io/log/run
{% endhighlight %}
