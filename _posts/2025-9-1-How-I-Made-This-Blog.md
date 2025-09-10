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
```html
your-username.github.io
```
This will also be the url to the website, unless you choose to purchase a domain and use that instead.
The easiest and least time consuming way to get a ready website is to fork someone elses repository, this is possible as github has a policy where the repository containing the website has to be public.

*Now i know some of you will say this is stealing, but isnt that what github is about, and anyway you only steal the framework, you have to do some work on your own afterwards to make it look like you want*

What I used is Barry Clark's repo, [repo-with-website](https://github.com/barryclark/jekyll-now), what you'll see is that its named *jekyll-now*, keywork jekyll. Jekyll is a ruby based static site generator that basically transform markdown into html, so even if you dont know html, you can still blog. 

You can read the guide in Barry Clarks repo like I did, but I'll write what I did here regardless, so you can have 2 sources. 

## Step-by-step guide

1. Fork the repository from [Barry Clarks github](https://github.com/barryclark/jekyll-now), and create your own repository named *your-username.github.io*. 
2. Installing ruby (WARNING: THE FOLLOWING SUBGUIDE IS ONLY FOR UNIX/UBUNTU SYSTEMS)
    1. My ubuntu system came with pre-installed ruby (system ruby), but downloading packages in the system ruby is not reccomended, as it can alter with the dependencies of the system version, also bad idea if you need multiple versions of ruby. The solution to this is a package called *rbenv*, it manages ruby installations, and can help you have a separate ruby environment for each project. 
    2. Install [rbenv](https://github.com/rbenv/rbenv?tab=readme-ov-file#basic-git-checkout)
    3. Install *rbenv install* (its on the github for rbenv), so you can download ruby versions freely, just make sure you install the necessary [build environment](https://github.com/rbenv/ruby-build/wiki#suggested-build-environment) beforehand.
    4. After installing *rbenv* and *rbenv install*, go into the terminal and check whether everything is okay with 
    ```
    rbenv versions
    ```
    You should see a single output named *system, * showing its the active version. 
    5. Now install ruby 3.4.5 by running
    ```
    rbenv install 3.4.5
    ```
    6. I'd also suggest you set the newly installed version as the global one, just so the system one is safe, run
    ```
    rbenv global 3.4.5
    ```
    7. Now go into the website's directory using the *cd* command, then you need to run:
    ```
    bundle init
    ```
    This will generate a Gemfile, in which you will then write *gem ""github-pages* (using a text editor like VSCode)
    8. Now that we've written the gem we need in our gemfile, we can go back to the terminal and run
    ```
    bundle install
    ``` 
    This will install all the ruby gems needed for our website, including jekyll, which is the most important one
    
3. Now that we have cloned the repository and we have installed ruby and all the gems we require we can start modifying the website to our wants
    1. First we need to modify all the variables in the _config.yml, you can check out how to do that in Barry's [tutorial-step-2](https://github.com/barryclark/jekyll-now)
    2. We then want to commit and push our changes to the remote repository we created (username.github.io), so that github can sense we are making changes and deploy the website to, in my case [david-tsankov.github.io](david-tsankov.github.io)
        * We can commit in 2 ways, first is to use VSCode's built in GUI and press commit, and then sync changes
        * Second way is through the cli (terminal), you do that by first going into the site directory using *cd*, then run
        ```
        git add .
        ```
        After that you want to 
        ```
        git commit -m "Your commit message"
        ```
        And finally
        ```
        git push
        ```
        Now, on the final step (git push), the terminal will ask for your username and password, the password however is not your normal github password, but a github token that you need to generate separately, additionally it has to be a classic token, you can take a look at this [guide](https://www.geeksforgeeks.org/git/how-to-authenticate-git-push-with-github-using-a-token/) for more info.
    3. A very important feature is to be able to run your website locally, so that you dont have to wait for github to deploy the website every time you make a small change (you also have limited deployments per hour, or something of the sort), this is why we installed the gem *github-pages*. To run your website locally you need to run
    ```
    bundle exec jekyll serve
    ```
    Where bundle exec tells ruby to run the command only with the gems we have specified in the *Gemfile*, which is nice for not getting into a huge mess (i did a couple of times)  
    Note: NEVER RUN *SUDO GEM INSTALL* ON YOUR SYSTEM RUBY, BAD IDEA, HARD TO CLEAN UP.  
    After that you can check out your website on the ip written after the command, usually *127.0.0.1:4000*
    4. Now that we can run the website locally and have it run on github with no issues, its time to change the contents of the website, this is the hardest part, as while I tried avoiding having to learn html and css, trying to change the contents and look of the website has forced me to gain at least a small idea of how it works. 
    5. Personally I will be using the website to upload math related content, so I had to find a way to implement math syntax support, I did this by implementing MathJax, by following this [guide](https://webdocs.cs.ualberta.ca/~zichen2/blog/coding/setup/2019/02/17/how-to-add-mathjax-support-to-jekyll.html)
    This allows me to write mathematical expressions, as long as they are in between 2$-signs, e.g. 
    ```
    $$y=\frac{x+1}{x-3}$$
    ```
    Is the code for $$y=\frac{x+1}{x-3}$$
    6. To change the styling of the website you should look at *style.scss* file and check out the different elements of the html and their styling, e.g. go to the style.scss file and scroll down to the .wrapper-footer element, there it has the property *background-colour* that is probably set to $lightGrey, you can change that by substituting $lightGrey with whatever colour you want, by either writing the code of the colour, or creating a variable corresponding to the colour code in *-variables.scss*, you do that by writing the following:
    ```
    $Colour-name: #52ab98;
    ```
    Where the #52ab98 is the colour-code, then you can use the variable *$Colour-name* in place of $lightGrey.  
    You can do that for other elements by first checking the html and understanding what each element represents, then going to the style.scss and changing its properties (colour, size, font). Have in mind that if you want to use a font you first have to import it on the top of your style.scss


---
This concludes the guide, it's not prefectly complete, and is mostly valid about Linux systems, so it would be beneficial if you only use it as a framework rather than a strict step-by-step process as each machine and operating system will behave differently.  
$$Good \ luck$$ and check out my [github](https://github.com/david-tsankov)

