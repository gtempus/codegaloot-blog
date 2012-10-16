---
layout: post
title: "Are You Greater Than the Sum of Your Tests?"
date: 2012-10-11 21:19
comments: false
categories: [testing, design, agile] 
---

A similar question I was also asking was, "Are your unit testing mumbo jumbo diciplines just a crutch?" It's a question that has been nagging me recently; especially after making my latest career move. Thankfully, the answer hit me like...well...

{% img http://www.publicdomainpictures.net/download-picture.php?adresar=20000&soubor=stacked-bricks-2961292419383XVm.jpg 400 300 'A Ton of Bricks' 'a ton of bricks' %}

"It's not about the tests, dummy!" I blurted out to myself. The tests enforce a set of well respected and battle tested principles if you are listening to them and are aware of the pressures they are exerting on your code. I have written really worthless tests and I have also used tests to write some very elegant code. I have learned that you can cleave gobblins with extreme prejudice but you can just as easily commit harakiri.

Johnathan Rasmusson reflects on this in his [It's not about the unit tests](http://agilewarrior.wordpress.com/2012/10/06/its-not-about-the-unit-tests/) blog entry. Reading Johnathan's post made me go back and revisit Michael Feathers' [The Flawed Theory Behind Unit Testing](http://michaelfeathers.typepad.com/michael_feathers_blog/2008/06/the-flawed-theo.html) article that I had read a few years before.

Both gentlemen make the exact same assertion - Unit Tests != Quality

My ephiphany came on the heels of two recent events:

First, after instrumenting a project with gtest I had made a few exemplar tests to show my collegues popular strategies for getting the legacy code into the harness. I had left for them what amounts to code still on the operating table. Sure the tests passed and I had been able to map the functionality to something of a user story but to another trained eye the patient still hadn't been sown up. Before long I was informed that one of my teammates had added some 54 more tests to the same library of code as my original example code...automatially...with a script...and a template. Doh!

Second, I was working on an automated unit testing presentation for work and had this sinking feeling that I wasn't covering the topic 

Photo Credit: [Stacked Bricks](http://www.publicdomainpictures.net/view-image.php?image=10824&picture=stacked-bricks "Stacked Bricks") by Peter Griffin