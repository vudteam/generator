---
layout: post
current: post
cover: assets/images/io.png
navigation: True
title: How To Write Posts Up
date: 2018-08-19 12:00:00
tags: beginner-series
class: post-template
subclass: 'post'
author: theinfecteddrake
---

So this article is based upon how to writeup posts here on this blog.

### Requirements:

- Git installed and some knowledge of using `git`.
- A Ruby environment.

### Follow the steps below :

- So first of all head over to Github and clone the repo named `generator`. This is the main stuff which is going to help you to write posts up. This is the main posts generator.
- Once you have downloaded it, you will need `bundler` to install all the dependencies. Oh and don't forget to update your Ruby. A `gem install bundler`/`gem update bundler` will get you the latest version of `bundler`. Install the dependencies in the Gemfile via `bundle install`.
- When you are done with dependencies, navigate to the `_posts/` folder within the `generator/`.
- Now here comes the most tricky part of it, __observe the pattern in which the files are named__. Now when you write up a post, your file has gotta be named in the same pattern `<date>-<topic_name>`. the `<topic_name>` will be the file name which will appear when the final post has been generated.
- Open up any post and __observe the pattern in ehich they are written__. I purposefully, made this stuff offline since I think online editing and stuff are trash and they offer less moderation to revisions and stuff.

So lets open up the file named `2018-08-11-coding-this-stuff-up.md` and lets analyse this properly.

1. So take a look at this part within the two `---`s:
```
---
layout: post
current: post
cover: assets/images/bs.jpg
navigation: True
title: Coding This Stuff Up
date: 2018-08-11 12:00:00
tags: networking
class: post-template
subclass: 'post'
author: theinfecteddrake
---
```
So this is the main part that fetches the layout-
- `layout` - Defines the layout.
- `current` - Tells the generator about the layout.
- `cover` - Your choice of cover image under `assets/images/` directory. Put your own cover photo (preferably of a reasonable resolution) and include the name here.
- `title` - The title of your post. This will appear as in big letters at top of your post (so choose this wisely). Also note that your post title must be similar to your filename.
- `date` - Self explanatoy I guess. Time should __NOT__ be in future (I ran into this problem and had to google the whole internet for fixing it :(.
- `tags` - An imp. part. You post must be of a specific tag so as to make it discoverable. If you want to view tags, go ahead and navigate to `_data/tags.yml`. There you can add your own tags (if you wish).
- `author` - Your username. To view what username you have, visit `_data/authors.yml`, everything is self explanatory there.

###### Note:-
Do not change the attributes such as `layout`,`current`,`class`,`subclass`.

2. Now comes the main body part, as you can see everything is in markdown (I hope you all are familiar with it ;_;).
3. Simply straight away start writing into the point. DO NOT write the site title heading again, for it will appear twice (not a good idea).
4. Finish the article as per your need. ;)
5. Now here comes an important part. Name your article as per your heading (try to keep it short). and put it in the `_posts/` folder. Make sure your cover image is there in `assets/images` folder and the refernce has been made in the `cover` attribute. Double check everything for typos and stuff (this is why I preferred this offline).
6. Now visit the root directory of `generator/` folder, open up a terminal and run `bundle exec jekyll serve`. This will start your page generation under `generated-pages/` directory. Also this will start up a server on port 4000. Visit `localhost:4000` via browser and take a look at the generated stuff (I mean your post). You can edit the post in your IDE itself (incase you want to) and take a look at the changes wich be automatically loaded into the browser.
7. Once satisfied, initialise an empty git repo and add the remote location of `https://github.com/vudteam/blog` to the `generated-pages` folder, then fetch the contents, remove the mixed differences, and set the tracking up to the master branch of the remote repo.

Whatever I told, if doesn't make sense to you, simply follow these steps after opening a terminal in the `generated-pages/` folder. Make sure `git` is updated:
```
rm -rf .git
git init
git remote add origin https://github.com/vudteam/blog
git fetch
git reset --mixed origin/master
git branch --set-upstream-to=origin/master master
```
__->__ Then commit your file via:
```
git add <your filename>
git commit -m 'Added post'
```
Push your changes via `git push` to the branch. You will be asked for credentials, enter the credentials as given. Your changes will be published on GitHub, and hence on website. ;)

Thats it! give it some 5 mins. for your changes to come online. Refresh your browser and you will see your article has been added on website!

I know this is a bit of heck, but this is the only time you will have do this for the setup ONLY ONCE.

Now next time you write a post:

- Use `git pull` to update your local repo if any other person has added a post.
- Start from the commit part denoted by `->`. Add your file, commit it and push.

Congo, you're are done!
