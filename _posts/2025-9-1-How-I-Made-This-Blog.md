---
layout: post
title: How I made (stole) this blog
tag: Software
usemathjax: true
---

## This post is about how I made, or rather stole this website and how you can do it too. 

This website is a static site, meaning once the server deploys the website on the web, the viewer (you in this case), cannot do anything to change the contents displayed on it. 
The cheapest way to host a static website, from my research, is through github, as they have a feature called github pages, where each user has the right to a single static website where they can post non-business related content. You can check it out here ---> [github-pages](https://docs.github.com/en/pages)  
### Why github pages is nice
The main thing github pages has on other platforms is how easy it is to deploy the website (its also free :O)  
The way you deploy the website through github is through a repository named in the following way  
>your-username.github.io

This will also be the url to the website, unless you choose to purchase a domain and use that instead.
The easiest and least time consuming way to get a ready website is to fork someone elses repository, this is possible as github has a policy where the repository containing the website has to be public.

*Now i know some of you will say this is stealing, but isnt that what github is about, and anyway you only steal the framework, you have to do some work on your own afterwards to make it look like you want*

What I used is Barry Clark's repo, [repo-with-website](https://github.com/barryclark/jekyll-now), what you'll see is that its named *jekyll-now*, keywork jekyll. Jekyll is a ruby based static site generator that basically transform markdown into html, so even if you dont know html, you can still blog. 

You can read the guide in Barry Clarks repo like I did, but I'll write what I did here regardless, so you can have 2 sources. 

## Step-by-step guide

1. Fork the repository from [Barry Clarks github](https://github.com/barryclark/jekyll-now), and create your own repository named *your-username.github.io*. 
2. Install ruby by running (WARNING: this is for DEBIAN/Ubuntu systems)
```
sudo apt-get install ruby-full
```
