---
layout: post
title: "How to Set Up a Custom Octopress Blog"
date: 2015-06-11 13:37:02 -0400
comments: true
categories: ["Flatiron School", "Tutorial", "Octopress", "Blog"]
---
Blogging is great for developers at any stage in their coding career. Today I'll be going over how set up an Octopress blog. Octopress is a static blogging framework that utilizes Jekyll.  Wait a minute. Let's break that down.  

###Static 
A static web page is a page that does not change user to user.  The content that is displayed will be the same, no matter who views it.  

###Blogging Framework 
A blogging framework allows a user to make changes to their blog with minimal coding.  The framework takes care of the major code, so that the user can create the content easily. 

###Jekyll
Jekyll is the underlying framework. Jekyll creates templates that are stored on your computer and used to build the web pages of your blog so that the server does not have to.  This allows the website to be loaded quickly. 

Now that we've covered that, let's get started! 
#Step 0 - Initial Setup
If you haven't already, create a <a target=_blank href="https://github.com/">GitHub</a> account!  Don't worry about making a GitHub repository quite yet.  Next, create a local directory on your computer for your blog.  This should be someplace that you will remember easily, so that you can find it when you want to make a post.  Once you have that created, use the command line to get into that directory.  If you do not have experience with the command line, try out this <a target=_blank href="http://lifehacker.com/5633909/who-needs-a-mouse-learn-to-use-the-command-line-for-almost-anything">tutorial</a>.  Primarily focus on how to navigate directories.  You're also going to need a text editor.  I suggest <a target=_blank href="http://www.sublimetext.com/">Sublime Text</a>, but you can use any editor designed to edit plain text.
  
#Step 1 - Getting Octopress
Once you are in the directory that you want your blog in, run the following commands using your command line: 

``` sh
git clone git://github.com/imathis/octopress.git octopress
cd octopress
bundle install
```
In the above code snippit we are first cloning, or making a copy, of <a target=_blank href="https://github.com/imathis/">imathis</a>'s  repository, which is called <a target=_blank href="https://github.com/imathis/octopress">octopress</a>, from GitHub.  Then, we are moving into the octopress folder.  Next we are installing the ruby gems specified in the Gemfile. 

#Step 2 - Getting Rake
Rake allows us to automate tasks.  This makes many tasks related to our blog a lot easier.  In the command line, type the following command: 

``` sh
rake install
```

Oh no! Did that throw an error? Don't worry! If that didn't work for you, enter the following commands: 

``` sh
bundle exec rake install
rake install
```

We've done a decent amount, so let's commit what we've done to git. 

``` sh
git add -A
git commit -m "Creates and sets up my basic octopress blog"
```
The first command tells git to track all the new additions or deletions in the directory that we are currently in.  The next command commits these changes to git with a message.  The message can be anything, but it's best to describe what changes you are committing.

#Step 3 - Setting Up _config.yml
It's time to view your files in your text editor. If you are using Sublime Text, you can do this by typing `sublime .`.  Once you have the directory open in a text editor, navigate to the `_config.yml` file.  You should see a block of code similar to the code below: 

``` 
title:                                  # Used in the header and title tags
subtitle:                               # A description used in the header
author:                                 # Your name, for RSS, Copyright, Metadata
description:                            # A default meta description for your site
```
Fill out each of these fields with information about your blog.  When you're done, it should look something like this, but with your information: 
``` 
title: A Very Amazing Blog              # Used in the header and title tags
subtitle: Blogging With Octopress       # A description used in the header
author: Jane Doe                        # Your name, for RSS, Copyright, Metadata
description: A blog about Octopress     # A default meta description for your site
```
This was a big step, so let's commit to git again. 
``` sh
git add .
git commit -m "Configures _config.yml"
```
This time we used `git add .`, which will add all additions to git, but leave out any deletions.  We did not make any deletions, so this will not cause any problems at this point.  You could also use `git add -A`, which in this case would complete the same action.

#Step 4 - Hosting Octopress on GitHub
We are going to be using <a target=_blank href="https://pages.github.com/">GitHub Pages</a> to host our blog.  First, create a new repository on GitHub called username.github.io.  Username should be replaced with your GitHub username. Make sure the check box that initializes the repository with a README is *UNCHECKED*.  Next, we are going to put our blog into the repository that we just created.  From the command line, enter the following command: 
``` sh
rake setup_github_pages
```
Next, you'll see: 
``` sh
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io.git')
           or 'https://github.com/your_username/your_username.github.io')
Repository url:
```
Go back to your repository on GitHub.  Find Quick Setup and set it to SSH.  Copy the URL provided and paste it into the your terminal.  The result should look something like this, with your information as the url. 
``` sh
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io.git')
           or 'https://github.com/your_username/your_username.github.io')
Repository url: git@github.com:tibsar/tibsar.github.io.git
```
*So what did we just do?*

* The `url:` line in `_config.yml` was changed to contain the url of your blog
* You were moved to a new `source` branch, where all editting of your blog will occur 
* You were given access to push your blog to GitHub

Since we can now push our blog to GitHub, let's do that using `git push origin source`.

#Step 5 - Writing A Post
You officially have a blog! That means it's time to make our first post. Go back to the command line and enter: 
``` sh
rake new_post["My First Post On Octopress"]
```
The string in quotes within the brackets is the title of the post.  You can make the title anything, but it should probably have something to do with the content of the post. Now, go back to your text editor.  Navigate to the `source/_posts/` folder.  This is where all of your posts will be stored.  Right now, there should only be one file, with the date and title of your post as the file name.  Open that file and find something along the lines of: 
``` 
---
  layout: post
  title: "My First Post On Octopress"
  date: 2014-04-28 13:03:17 -0400
  comments: true
  categories: 
---
```
You can add categories into the categories section that relate to your post.  To enter multiple categories, you can use the syntax `["cats", "octopress", "babies"]` The content of your post will go under the second `---`.  You can write anything here! Since it's the first post though, you may want to keep up tradition with "Hello world!"
``` 
---
  layout: post
  title: "My First Post On Octopress"
  date: 2014-04-28 13:03:17 -0400
  comments: true
  categories: ["Octopress", "Hello World"]
---
Hello world!
```
If you want to see what your post is going to look like, before you deploy it, simply enter: 
``` sh 
rake preview
```
This will start Octopress locally.  To see our blog, open a web browser and go to `localhost:4000`.  You can now see what your blog is going to look like! If you don't like the look, don't fret.  We will be going over how to customize your blog in another post.  When you are done previewing your blog, you can stop by hitting `ctrl + c` on your keyboard.

#Step 6 - Deploying
Now that we have a post, we need to know how to get our blog online. Go back to the command line and enter: 
``` sh
rake generate
rake deploy
```
 Now, we should send all of our changes up to GitHub. Do you remember the commands from earlier? 
``` sh
git add -A
git commit -m "adds my first blog post and deploys my blog"
git push origin source
```
Congratulations, you now have an Octopress blog! Now test it out! Go to `username.github.io` in a web browser to see your newly deployed blog.  If you love your blog, but hate how it looks, checkout <a href="/blog/customizing-your-octopress-blog/" target=_blank>Customizing Your Octopress Blog</a>. 