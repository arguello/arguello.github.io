---
layout: post
title: "Try Code - An Interactive Guide"
description: "Introducing Try Code, your ultimate online, interactive resource for learning to code."
keywords: "racket, code, learn to code, try code, hour of code, programming, trycode.io, nginx, jquery-console"
date: 2015-03-03 17:00:42
permalink: trycode.io
published: true
categories:
  - Racket
  - programming
  - REPL
  - trycode.io
---

It's with great pleasure that I announce <a href="http://trycode.io" target="_blank">Try Code</a> - an online, interactive coding tutorial for those with absolutely no programming experience.

<a href="http://trycode.io" target="_blank">Try Code</a> is a simple tutorial which introduces coding in a fun, friendly and interactive way - through a simple <strong>Guess My Number</strong> game.

It focuses more on learning to code than on the nuances of a specific language. Although <a href="http://racket-lang.org/" target="_blank">Racket</a> is the language used throughout the guide, my goal was to focus more on general programming concepts and terminology, with a bit of history and math thrown in for fun.

The tutorial content itself is condensed from Chapter 2 of the book <a href="http://realmofracket.com/" target="_blank">Realm of Racket</a> - an awesome book that teaches you to code <em>one game at a time!</em>

###How I Did It
Simple. I forked jarcane's <a href="https://github.com/jarcane/try-racket" target="_blank">Try Racket</a>.

I did change the design and added some functionality - which meant I had to brush up on CSS and JavaScript - but <a href="https://twitter.com/J_Arcane" target="_blank">jarcane</a> (and others) did most of the heavy lifting.

As a side note, I firmly believe that JavaScript is a practical joke that got out of hand; like <a href="http://www.soylent.me/" target="_blank">Soylent</a>. Or Windows ME. Or Kim Kardashian.

Try Code does use a <a href="http://docs.racket-lang.org/web-server/index.html" target="_blank">Racket Web Server</a>, which sits behind a <a href="http://nginx.com/resources/admin-guide/reverse-proxy/" target="_blank">nginx proxy</a> - and both are managed through <a href="http://cr.yp.to/daemontools.html" target="_blank">daemontools</a>.

The online REPL is built upon Chris Done's <a href="https://github.com/chrisdone/jquery-console" target="_blank">jquery-console</a>, which is a fantastic terminal emulator.

Anyone interested in contributing or reporting issues can do so at the Github repo: <a href="https://github.com/arguello/trycode.io" target="_blank">https://github.com/arguello/trycode.io</a>

###The Design
What you see on the site is actually the 3rd design - Ariel said my first design "was the same boring blue stuff you see all over the internet," and that the second design was much better - but she thought the site was for 6 year olds.

I wanted the design to appeal to all sexes, and I settled on the <a href="http://ethanschoonover.com/solarized" target="_blank">Solarized Light</a> color scheme. It's inoffensive and easy on the eyes.

It uses the <a href="http://getbootstrap.com/" target="_blank">Bootstrap Framework</a>, which made things easier at first.

###Bigger, Faster, Stronger
I plan on adding more to <strong>Try Code</strong>, and it will be awesome.

It will continue to revolve around games, although I would like to push out a math tutorial as well. And a web tutorial. And something around science.

Follow me <a href="https://twitter.com/ffdtm" target="_blank">@ffdtm</a> for updates, and feel free to offer suggestions. Or content.

###What's Up with Gabby and Ariel?
Ariel and I are still making our way through <a href="http://www.nostarch.com/realmofracket.htm" target="_blank">Realm of Racket</a>. She felt that Chapters 3 and 4 were like "homework", whereas I found them to be very useful; but we're back into the games and she's having fun again. I do plan on maximizing my time by getting Gabby caught up and working with her and Ariel at the same time.

<a href="http://meta.fja.io/fledgling-lisper/" target="_blank">Gabby didn't want to start until she took her ACT exam</a>, which is scheduled for today. We did run through some math with Racket, which really excited her - she's in her school's math club - and we did the <a href="http://docs.racket-lang.org/quick/" target="_blank">Quick</a> tutorial together. She enjoyed that, and we'll start on the Realm of Racket this weekend.
