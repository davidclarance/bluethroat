---
title: "Setting up a blog with Hugo"
date: 2019-12-23T02:01:58+05:30
description: "Why and how I set up this blog"
tags: [tutorial]
---

## Why blog?

*Feel free to jump to the next section if you just want to learn how to use Hugo to set up a blog.*

Writing helps me learn. Every time I want to learn a new technique, method or library I open up a sublime tab and type a lot. It helps me think, work through difficult logic and often helps pin point the source of difficulty. Writing in the form of journaling helps my mental health (I don't have a source for this, it just works for me). Working through how I'm feeling helps reduce stress, anxiety and all the other crap that comes with PTSD. And while I write a LOT, I rarely do it formally and rarely store what I write. Sublime tabs aren't saved, phone notes are deleted and written pages are thrown away. It's pretty therapetuic to dump ideas or thoughts and then just get rid of them. While I've done and enjoyed this in the past, I sometimes regret not saving notes, especially when it comes to working out the logic of new concepts. I also generally want to get better at language and writing well. So in 2020 I want to write 12 blogs or more about things I've learned. I'm not sure what these are going to be but I suspect these will be related to causal inference, coding in python and R and my new love for Microsoft's incredible editor VS Code. I might also throw in a blog or two about birds. Who knows?   

## Setting up a blog with Hugo

These instructions are windows users. I'd imagine that mac and linux would be similar. 

Before we start, what is Hugo? Simply put, Hugo's a framework for building static websites. Let's break that down. Hugo's a library or program or machine to produce websites that are not directly linked to a live server. So you can use Hugo to make websites that don't require constant updates in real time. This means that this is best suited to blogs or personal pages or documentation. 

So our final output is a folder that has a bunch of HTML files that we'll 'upload' to somewhere on the internet. 

### Step 1: Download Hugo

The first step is to download Hugo, the engine to create our website. You can go to this [link](https://github.com/gohugoio/hugo/releases) and scroll to the section that says assets. Scroll to the bottom and find the version of Hugo that corresponds to the OS you're using. So in my case because I have a Windows 64 bit machine, I used `hugo_0.61.0_Windows-64bit.zip`. Download the file somewhere on your computer. 

### Step 2: Creating a PATH variable to Hugo

It's super helpful to create a PATH variable to Hugo before you start on anything. This is the step that most online tutorials just assumed the user would do themselves. However it can be tricky if you don't fully understand what PATH variables are. PATH variables create a link between a command in the terminal and the file to run when you call that command. 

For instance, if I want to run MS WORD for the terminal (I don't know why I would want to), we can create a command called `word` and put it in PATH. How would we do this? We would need to put the destination (something like C:\Users\david.clarance\Word) which contains the word.exe file. So to create a PATH variable for Hugo do the following:

* Go to Control Panel > System and Security > System
* Click Advanced System Settings on the left tab
* Click on the Enviornment Variables button on the bottom left. 
* Find the variable that says Path in both the User and System settings. 
* Add a new item and put the directory where the hugo.exe file lives. So for instance, I created a new folder in my C drive and put the hugo.exe file in it. Then I added 'C:\Hugo\' to the path in both system and user settings. Note the slash after Hugo!  

Once you've done the above, open a new terminal/command-prompt window and type `hugo help`. You should see a list of commands. If there is an error that says that something's missing then you need to figure out what steps in the instructions listed above you missed or got wrong. 

### Step 3: Create a new Hugo website

Now that we've installed and put HUGO in our PATH. It's time to create a new website! 

Assume that I want to create a new website in a folder called david-hugo-blog in my Documents folder. So let's kick up a new terminal instance. And do the following

* Create a new folder in Documents called david-hugo-blog.
* cd to that directory in the terminal 
* Type the following:

``` 
-- cd to Documents in terminal 
> cd Documents

-- create hugo new website
> hugo new site david-hugo-blog
```

Once you've done this, there'll be a bunch of files and folders created in david-hugo-blog.      

### Step 4: Set a theme

Hugo is pretty powerful and [has a ton of themes](https://themes.gohugo.io/). You'll need to decide on one before you start. I chose the theme called [hugo-ink](https://themes.gohugo.io/) because I wanted something simple, clean and organized. Which ever theme you use, you'll need put it in the themes folder in david-hugo-blog. To do this, you'll need to have the path on github to the themes repository. Once you have this do the following:

(assuming you are in david-hugo-blog)
```
-- this takes you to the themes folder
> cd themes 

-- install the theme directly from git
> git clone https://github.com/knadh/hugo-ink.git
```

This will download the git repository for the theme into a folder called hugo-ink in the themes folder. 

Now, this is the bit thats a bit tricky. So follow these instructions carefully. 

1. In the hugo-ink folder, there's be a folder called exampleSite. Go to this folder.
2. From this folder copy the config.toml file and paste in the root folder for the website (for me this will be in the folder called david-hugo-blog)


### Step 5: Building the website. 

Once everything is ready, it's now very simple. cd to the root folder (david-hugo-blog) and then run the following commands

```
hugo server -t hugo-ink -d docs
```



---


