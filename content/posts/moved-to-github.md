+++ 
date = "2020-10-29T08:09:26+03:00" 
title = "Blog moving to GitHub" 
author = "Mats Hellman" 
description = "Moving my blog to GitHub." 
+++

It's the time of year when Wordpress.com is reminding me to renew my subscription
and since I really don't blog as much as I used to back in the days, the price
is just a bit to high.
  
## Hosting or not?

I started to look for a replacement service, initially I was thinking of hosting
my it on a virtual server somewhere as that's half the price of Wordpress. True
that it would make me manage the server but with ansible that would still be
trivial. First I was looking at [Linode](https://www.linode.com "Linode") as the
cheapest server was only a cup of coffee and this was reasonable for a monthly
price, and on it run Wordpress like I used to when I was really active.
  
As it sometimes happens, curiosity kicked in and I stared digging into static
site generators. And the simplicity they bring was pulling me in. I already
use MarkDown for a lot and looking at [Hugo](https://gohugo.io "Hugo") made
me even more curious if I could run everything from it.
  
Done and dusted, easy local installation with [Brew](https://brew.sh "Homebrew")
was screaming go,go, gooooo.

```bash
$ brew install hugo
```
  
Now the hosting, should it run on my rented hardware or not. After some
consideration I decided to try Github pages, for now this will be the solution
although I might change that in the future if I want to have a server running
somewhere again.

## Can it be this simple?

After installing and initializing my site locally I copied my blogposts from
wordpress to .md files. The simplicity is just amazing. The biggest headache I
had was to find a simple engough theme to use. After some trials I ended up with
[Etch](https://themes.gohugo.io/etch/ "Hugo Etch Theme"). It was simple enough
and I was able to get the few changes done I wanted.
  
The use of git and Github is also extremely nice, it just fits in my workflow.
Fits like a glove some would say, while we Finns say "Fits like a fist in the eye".
I can keep everything with me all the time, and when I change to a new device
everything is seconds away.