---
permalink: /about/
layout: single
title: "About"
excerpt: "The long history of HakuNeko."
single_layout_gallery:
  - image_path: /assets/images/about/legacy-linux.jpg
    alt: "HakuNeko for Linux (Legacy)"
  - image_path: /assets/images/about/legacy-windows.jpg
    alt: "HakuNeko for Windows (Legacy)"
last_modified_at: 2020-07-30
toc: true
---
# History

This section describes the curriculum vitae of HakuNeko.
Feel free to skip this boring stuff, this is something to read if you have to kill time ;)
{: .notice--primary}

## Necessity begets Ingenuity

The development of HakuNeko started around 2006/2007.
During this time i traveled alot between my home, family, friends, workplace and university.
Spending many hours in the train can become quite boring, so i thought about reading my favorite mangas on my notebook.
Reading online was almost impossible due to the lack of of mobile internet availability at that time.
So as a linux user i was looking for a convenient way to download some chapters from online reading websites to my notebook, but unfortunately there was no easy solution (although DomDomSoft was very popular for windows).
As a software developer the answer to my problem was quite simple:

> Don’t beg for things, do it yourself. Or you won’t get anything.  
> -- Axel Thurston, Eureka Seven

## When Naruto meets Nyan Cat

As a result the first version of my very own manga downloader tool was born and needed a cool name.
Anything including the terms _Manga_ and _Downloader_ seems way to boring, lets see... cats are always cool right (especially Nyan Cat)?
The japanese word for cat is _Neko_, so far so good, but not good enough as a distinguishing name for my tool.
How about combining it with another word like... _Black_ or _White_, which would lead to _KuroNeko_ or _ShiroNeko_?
Very nice, but somehow this sounds to mainstream.
Luckily one of the early Naruto epsiodes was running in the background and i recognized a character named Haku.
Purely on a whim i mixed both words together and from this very moment _HakuNeko_ was assigned as name for my tool.
I still don't know the meaning of the combination of these japanese words in english, but it sounds good and is unique.

## With Popularity comes Responsibility

Despite the fact that it was very basic and only had support for a few websites, it does exactly what i wanted:
Downloading mangas for offline reading on my next trip.
The application was written in C++ using the wxWidgets framework and therefore was available for Linux and Windows.

{% include gallery id="single_layout_gallery" caption="HakuNeko for Linux (Legacy) / HakuNeko for Windows (Legacy)" %}

Over the time HakuNeko improved and matured based on my personal needs, so i thought this piece of software might be useful for other users as well.
Eventually HakuNeko was published on some freeware downloading websites such as Softpedia and later an open source project was created on SourceForge.
In the first year it was not very popular (maybe choosing a name indicating that this tool is a manga downloader would have been smarter), but then slowly got momentum.
HakuNeko became more and more popular and it was no longer "My little Tool" to download mangas for reading in the train, it was now part of many other people's day to day life.
With the feedback from users who started to make suggestions, requested features and reported bugs HakuNeko evolved even more to meet all those expectations.

## Live Happily Ever After, or maybe not?

As time flew by, the development become stagnant.
The following list reflects the most significant problems:

- The old wxWidgets framework used in HakuNeko got removed from various linux distribution repositories and the migration to the new wxWidgets version caused much trouble and problems that could not be solved
- Users got downloading errors which could not be reproduced and getting fixed caused by the very bare-metal implementation around the CURL library
- Many websites started to improve their bot protections using sophisticated browser depending mechanics and the effort to bypass them was way to high

## The Next Generation

The end draws near.
HakuNeko was no longer able to cope with the upcoming challenges.
At the beginning of the year 2017 it was time for a rebirth.
The deciding requirements for the new underlying engine/framework were clear:

- Easy cross-platform development
- Incorporating a popular programming language and development tools (to attract potential contributers)
- Sophisticated integration of web-technologies (HTTP requests, DOM parsing, ...) and JavaScript engines (solving browser challenges)

It seemed to be impossible to fulfill all these requirements, but fortunately electron came to the rescue.
Being a "Customized Chrome Browser" it was perfectly suited for the revival of HakuNeko.
It didn't take long until the first prototype was finished with promising results.
The name _HakuNeko S_ was given to the prototype, but i can't remember what exactly the S meant that i simply appended to the name to distinguish it from the legacy version (maybe **S**uccessor or something?).
Based on the popularity of the legacy version it didn't take long until the users switchd over to the descendant.
As of today HakuNeko helps users from all over the world to achieve their goal: Downloading mangas for offline reading.
To me HakuNeko is more than a reliable manga downloader tool, it is software made from the heart.

![HakuNeko S for Linux (electron)]({{ "/assets/images/about/screenshot-pages.png" | relative_url }})
