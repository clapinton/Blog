---
layout: post
title: Configuring Jekyll
tags: jekyll, blog, github
---

## Research... research...
I didn't land straight on Jekyll. My needs were not fancy: I didn't want to give up my geeky side and go with a simple, WYSIWYG type of tool. I wanted a configuration which I could set up by myself and that would allow some level of tweak-iness. All in all, 4 things were on my mind:

* hosting (since this is an experience, I wanted something free so I could try it out first);
* tweak power (I wanted to get my hands dirty, so having access and being able to tweak the source code was imperative);
* setting it up and maintaining it had to teach me something! If I wanted a new feature, installing a plugin wouldn't teach me as much as going after an API and reading through the documentation to implement it. I wanted to feel challenged, damn it.
* migrating the content should be easy, so any CMS would have to allow some form of good csv export;

I found a <a href="http://thenextweb.com/businessapps/2015/05/11/the-18-best-blogging-and-publishing-platforms-on-the-internet-today/" target="_blank">bunch</a> of solutions, some of which I discarded on the spot:

* WordPress: it was my first choice, since I knew I could tweak and host for free, although there would be ads. Also, there are a bunch of plugins ready to use. But plugins are somewhat easy to install and wouldn't teach me as much);
* Posthaven `[discarded]`: paid and apparently basic;
* Ghost: Similar to WordPress. I could download and host myself or $8/mo for hosting;
* Kirby `[discarded]`: $15 for a personal license. Plus you host it yourself. Appears to have some PHP editing behind it, although focused on theme building, but the license is a deal breaker at this point. Besides, it's for personal only. Who knows how this will turn out;
* Medium `[discarded]`: No customization. I do love Medium's look and feel, but if I wanted that, I'd have started this directly there;
* Svbtle `[discarded]`: Limited customization.
* jekyll: it really caught my attention. Free (ok), very customizable (good), required command line knowledge (very good), has very good tutorials (keeps getting better), posts are static pages, which helps in load and migration (this might be the one);
* Anchor: interesting open-source option. Need to be self-hosted;
* Contentful: also interesting. Delivers content as API, so I'd code the interface and host it myself;
* TinyPress: very interesting. Jekyll-based application <a href="https://news.ycombinator.com/item?id=10409585" target="_blank">(according to dev)</a>, although it looks like one step ahead in terms of baked features;

The best fit was Jekyll, by far. It required (and allowed) me to geek out to set it up, and then geek out some more to get it to the point I wanted. Also, it taught me that I could host stuff on GitHub pages.

I had found what I was looking for.

## Setting up Jekyll

Setting up was interesting:

1. creating a page on <a href="https://pages.github.com/" target="_blank">GitHub pages</a> meant that I had to create a repo on GH, named exactly as the URL I wanted my page to have: clapinton.github.io;
2. git was already configured on my Mac, so I just had to clone the new repo on my local;
3. as for Jekyll, I needed to install it on my local through RubyGems, which I didn't have, so I installed RubyGems;
4. having that set up, it was time to `gem install jekyll`, which returned an error:

> ERROR:  While executing gem ... (Errno::EPERM) Operation not permitted

<a href="http://stackoverflow.com/questions/32891965/error-while-executing-gem-errnoeperm-operation-not-permitted" target="_blank">Apparently</a>, El Cap has some new security config which won't allow you to change some system files called Rootless, which aren't rootless, but more of "Root shall not pass!", since not even with root permission you'd be able to modify them for security reasons. I ended up installing the gem on the `/usr/local/bin` folder, instead of disabling Rootless.

For the last step, `jekyll new blog` created all the structured I needed, but it did that on a new folder, inside my blog already cloned git repo. One `mv` later and I had all the file tree exactly where I wanted, which meant it was time to test it on `localhost:4000`, which turned out to be A-OK!

I now had a local blog.

## Posting

I wrote a couple of posts, tweaked some vanilla text, went through the structure to see how much control I had (turns out, exactly how much I wanted) and finally dusted off my notes on git commands. A couple of `git push` later, I had my content online! w00t w00t

## What to do next?
That's what I asked myself before coming up with a [list of features](to-do-list.html) I wanted to build. I'll need to prioritize in the best Product Manager way possible :)

<br>
<br>
I'm finally wrapping my first official post, and I already know what to do next: taxes. No, I don't mean filing them. I mean writing about the thing and everything that I learned. What better way to "celebrate" tax season?