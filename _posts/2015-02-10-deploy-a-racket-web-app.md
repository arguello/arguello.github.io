---
layout: post
title: "Deploy a Racket Web App"
description: "How to reverse proxy a a Racket Web Server with nginx, and manage it with daemontools."
keywords: "racket, web server, nginx, apache, reverse proxy, trycode.io"
date: 2015-02-10 16:35:34
permalink: racket-web-server-nginx-reverse-proxy-daemontools
published: false
categories:
  - Racket
  - web application
  - nginx
  - reverse proxy
---
You created a Racket Web Application, and you want to deploy it - but how?

I opted to host my app on a <a href="https://www.digitalocean.com/?refcode=997e653df36e" target="_blank">Digital Ocean</a> *droplet* (which is just clever marketing-speak for Virtual Private Server, or *VPS*).

After provisioning a droplet with Ubuntu 14.04 x64, I updated my domain to use Digital Ocean's name servers. I added an A record that pointed to my droplet's IP, and a *www* CNAME that referenced my A record.

So, now I have a server, and my DNS is handled; but how do I get my Racket Web App up for public consumption?

###Apache
I had mapped my domain name to my droplet, but not to my Racket Web Server - and I wasn't sure that I wanted the public to have direct access to it.

A quick Google search led me to <a href="http://docs.racket-lang.org/web-server-internal/Troubleshooting_and_Tips.html" target="_blank">The Racket Web Server Troubleshooting and Tips</a> page, which has a section on using Apache to proxy requests to a Racket Web Server. Ooh, proxies!

Now, <a href="http://en.wikipedia.org/wiki/Apache_HTTP_Server" target="_blank">Apache</a> is awesome - it has remained the most popular HTTP server since April 1996. In 2009, it became the first web server software to serve more than 100 million websites. In my case, however, using Apache would be like stuffing 10 pounds in a 5 pound sack.

In some circles, <a href="http://nginx.org/en/" target="_blank">nginx</a> is the undisputed king of reverse proxy servers. Its lightweight, performant, and scalable; and its known for having low memory usage - which makes it great for a VPS. And I'm hosting my site on a VPS.

###By Proxy Request Only
My plan was to lock down my Racket Web Server by placing it in a non-public subnet (for its own good, of course; not because its coded in a minority language), and I decided to provide access through an <a href="http://nginx.com/blog/reverse-proxy-using-nginx-plus/" target="_blank">nginx Reverse Proxy</a>.

Reverse proxies are cool - they provide benefits such as:

* security
* caching
* serving static content
* caching
* compression
* redirects/url rewrites

I decided to use all those features.

####Installing and Configuring nginx
Installing nginx is as simple as:
{% highlight bash %}
sudo apt-get install nginx
{% endhighlight %}

And configuring an nginx reverse proxy is as simple as:
{% highlight nginx %}
server {
      server_name domain.tdl; # your web app's domain name
      proxy_pass  http://127.0.0.1:8080; # ip:port of your racket web server
}
{% endhighlight %}

I also wanted to redirect all *www* prefixed urls to the base url (from http://www.trycode.io to http://trycode.io), and https to http:

{% highlight nginx %}
server {
      server_name www.trycode.io; # domain to redirect from
      rewrite  ^/(.*)$  http://trycode.io/$1 permanent; # redirect to
}
{% endhighlight %}

The above uses a 301 redirect, which helps with SEO.

I also added caching; you can see the full config <a href="https://gist.github.com/arguello/9a25162d49e37df84e87#file-default" target="_blank">in this gist</a>.
