---
title: My Hacker School FizzBuzz Program
author: Ben Brittain
date: September 12, 2012
---

So, I just finished up building this blog using hakyll (a static site generator library for haskell). As an inaugral post to ensure the capabilities of it, I'm publishing a little article about one of my favorite programs I've written (or seen in general).

A little history: Way back in April of 2012, I was in Cleveland visiting my family for passover. Late at night while I was avoiding family, I stumbled across an article on Hacker News about [Hacker School](https://www.hackerschool.com). It seemed like the ideal way to spend a summer... writing Open Source software with a bunch of awesome programers in NYC? count me in. The application was pretty sparse, it essentially asked for a link to github, a couple of opinion questions, and for a [fizzbuzz](http://c2.com/cgi/wiki?FizzBuzzTest). 

I was a little worried about standing out. I didn't have much on my github & who knows if they are answering opinion questions correctly? I needed to shine with my fizzbuzz. I've always been amused by esoteric programming languages like [Malbolge](http://en.wikipedia.org/wiki/Malbolge) and [BrainFuck](http://en.wikipedia.org/wiki/Brainfuck). After looking around, I decided I'd spend the 4 hour train ride back to Rochester (where I attend RIT) writting a program in piet. 

[Piet](http://www.dangermouse.net/esoteric/piet.html) is a pretty cool language. It's designed to look like the work of Piet Mondrian, a famous pioneer in abstract geometric art. Sure, the artistic purists will argue that Mondrian only used primary colors... oh well, those pastels look pretty. The actual source code is the image, usually a .PNG or .PPM file. Every block of color gets a numerical value based on the color's surface area. Operations are performed depending on the change in hue or lightness.

![fizzbuzz](images/FizzbuzzLarge.png)

here is trace made by the [npiet](http://www.bertnase.de/npiet/) interpreter. If you are interested inwriting a piet program, I highly advise using the npietedit tool. I really wish I had known about it when I wrote this program in gimp.

![trace of fizzbuzz](images/FizzbuzzLargeTrace.png)
