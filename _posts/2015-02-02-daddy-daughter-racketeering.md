---
layout: post
title: "Daddy-Daughter Racketeering"
description: "Teaching my daughter to code - why I chose the Racket programming language and the book Realm of Racket."
keywords: "racket, realm of racket, coding, girls who code, lisp"
date: 2015-02-02 21:18:31
permalink: daddy-daughter-racketeering
categories:
  - Lisp
  - Racket
  - Programming
  - Girls Who Code
---

My daughter Ariel asked me to teach her to code. She wants to be a programmer.

I'm ridiculously proud of her! Following in her old man's footsteps! She is clearly a brilliant diamond amongst the rubble of her generation!

I better not screw this up.

So, after much thought and careful consideration, I decided to help her learn how to code through the <a href="http://racket-lang.org" target="_blank">Racket</a> programming language.

##Why Racket?

My introduction to programming was rough, and had me questioning my intelligence, intestinal fortitude and career options - I wondered why anyone would want to be a professional coder? A little back story:

###A Grunt's Not So Gentle Intro to Computering

I was a soldier once, an <a href="http://en.wikipedia.org/wiki/Infantry" target="_blank">infantryman</a> in the Army's <a href="http://en.wikipedia.org/wiki/10th_Mountain_Division_(United_States)" target="_blank">10th Mountain Division</a>. After serving 4 years, I reenlisted for an additional 6 years, and was able to get a semester of college as part of my contract.

At that time, I had owned a computer for about 3 months. I bought the cheapest Gateway available, and my dial-up modem connected me to a fascinating virtual world at 56 kbit/s - email, ICQ, Napster, E*TRADE, Unreal Tournament - and I wanted to be more than an end-user.

So, I enrolled at Jefferson Community College in Watertown, NY; and signed up for an introductory programming class. The language: COBOL

###WTH is a COBOL?

To me, it sounded like some kind of futuristic super-tech wielded by NASA rocket science physicist hackers. Probably created by Einstein during his stint at the <a href="http://half-life.wikia.com/wiki/Black_Mesa_Research_Facility" target="_blank">Black Mesa Research Facility</a>.

I quickly learned that wasn't the case. <a href="http://en.wikipedia.org/wiki/COBOL" target="_blank">COBOL</a> was designed to be a common business language. I knew nothing about business, and I was ignorant as to the inner workings of computers. In fact, this was my first computer class of any kind, and I was in over my head.

The professor talked about how much simpler COBOL was when compared to the punch cards used when he started programming. I thought writing COBOL was slightly more preferable than a steel-toed kick to the nether regions.

Any doubts I had about a career in the Army dissipated as I continued that class - I was a good soldier, I enjoyed it, and I could pretend that COBOL never happened.

###You Don't Have to Teach Her COBOL!

I know, I know - but that experience made me very cautious about programming languages, or at least *first* programming languages.

I had no expectation that learning to code would be easy or fun, but I also didn't expect it to suck so bad.

###How About Python or Ruby? They're Easy-ish

I work with both languages, and I really enjoy coding in Ruby. It had occurred to me that Ariel might like building a Sinatra or Ruby on Rails app/site.

She would also have the opportunity to learn html, css, erb, and javascript. Or coffeescript, haml, and slim. Bootstrap and AngularJS. And I could teach her how to use Vim, or Rubymine, or Atom, or Sublime Text.

Wow, that escalated quickly.

Ariel is 15 years old, on her high school Drill Team, and enrolled in honors courses. Her time is limited, and I don't want to overwhelm her or take the focus off of programming fundamentals.

Then I thought that she could <a href="http://learnpythonthehardway.org" target="_blank">Learn Python the Hard Way</a>, but why not learn to program in a simple and fun way?

Granted, there are other avenues to learning Ruby or Python, and it was while researching those other options that I discovered <a href="http://racket-lang.org" target="_blank">Racket</a>, a member of the <a href="http://en.wikipedia.org/wiki/Lisp_(programming_language)" target="_blank">Lisp/Scheme</a> family of programming languages.

###Wait, Aren't Lisps Supposed to be Hard?

Lisps appear to have reputations as relatively hard-to-learn languages wielded by <a href="http://lispers.org" target="_blank">aliens</a> and/or artificially intelligent academic mathematician PhDs (often one and the same), and I wasn't ready to commit without further research.

My first foray into Racket was through the traditional **Hello World** program:

{% highlight racket %}
#lang racket
"Hello, World!"
{% endhighlight %}

Hmmm, that was easy. And why does Racket come with an <a href="http://en.wikipedia.org/wiki/Racket_(programming_language)#DrRacket_IDE" target="_blank">IDE</a>? And a <a href="http://en.wikipedia.org/wiki/Read–eval–print_loop" target="_blank">REPL</a>?

It's almost as if Racket was meant to be easy to learn.

Perhaps a little too easy?

Could it be a trap?!!

Treading carefully, I tried <a href="http://docs.racket-lang.org/quick/" target="_blank">An Introduction to Racket with Pictures</a>. Simple and cool. I started thinking that the Lisps have an undeserved reputation. All the same, Ariel would need more than a quick introduction.

So, I continued my recce, and found the book <a href="http://www.amazon.com/Realm-Racket-Learn-Program-Game/dp/1593274912/" target="_blank">Realm of Racket: Learn to Program, One Game at a Time!</a>

###Enter the Realm of Racket

Now, I'm no conspiracy theorist - but either the Lisp naysayers are a group of slanderous, libelous malcontents; or Racket wants to lure me into it's lair and fatten me up on parenthesis and lambdas before laying waste to my Ruby gems and Python eggs.

But... <a href="http://realmofracket.com" target="_blank">Realm of Racket</a> looks good, really good. It has <a href="http://realmofracket.com/about.html" target="_blank">11 authors</a> (can you say peer-review?), and it appears to gradually introduce programming concepts in a gentle and fun way. And there's the simple Racket install, with the included IDE and REPL.

###Racket FTW!
OK, DrRacket, you sexy beast, you twisted our arms - we'll enter the Realm of Racket and learn your syntax, dialects, macros, libraries and whatnot.

We'll wade into your parenthetical depths armed with nothing more than our wits, <a href="http://www.nostarch.com/realmofracket.htm" target="_blank">a map</a>, and a broadband connection to your <a href="http://lists.racket-lang.org" target="_blank">mailing lists</a> and <a href="http://racket-lang.org/irc-chat.html" target="_blank">freenode IRC channel</a>.

And we'll emerge as full-fledged Racketeers, with hard earned muscle memory mappings to Shift+9 and Shift+0.

But first, we need a plan.

##Our Plan

1.	Lambda Tattoos - to demonstrate our commitment to Racket (King of Lisps), Ariel will mark the lambda symbol (λ) onto her ankle and I'll tat it thug-style on the side of my neck. We'll rinse away the ink residue and blood with grape Kool-Aid.
2.	Realm of Racket - every chapter, every exercise, in order. We will do this somewhere fun (boba tea house or froyo joint), at least 2 nights per week.
3. DrRacket - we will keep things simple by using the provided development environment.
4.  <a href="http://lists.racket-lang.org/users/" target="_blank">Racket Users</a> and <a href="http://racket-lang.org/irc-chat.html" target="_blank">#racket</a> - for any questions or help that we might need from the experts - sort of like office hours, but without the tuition.
5.	OSS Project - TBD. We'll either contribute to an existing project, or start our own. Or both.

We'll actually skip Step 1, but we still plan on having fun ;)
