# niftools.github.io


## Running Locally

You need to install Ruby. After you install Ruby you can simply install Bundler:  `gem install bundler`

Then to get the necessary gems for the site you run `bundle install` from the project root.

You will most likely get an SSL error while trying to build so you need to grab [http://curl.haxx.se/ca/cacert.pem](http://curl.haxx.se/ca/cacert.pem) then install it anywhere (e.g. Ruby folder) and add it to your `PATH`.

`OPTIONAL` If you want to edit or create posts more easily (instead of by hand), you can uncomment `- jekyll-admin` in `_config.yml` to use the admin interface at localhost:4000/admin.  This change does **not** need to be committed as `jekyll-admin` is local only.  I would recommend leaving it otherwise commented as it appears to disable file watching while editing the site design.

`OPTIONAL` If you are ever designing new pages and need to change `\bower_components` in order to add package dependencies you will need to install Node.js/npm.  You must then install Bower with `npm install -g bower`.  From there you can add Bower packages to the project root's bower.json and then run `bower install` or you can run `bower install <package>`. 


## Front-Matter

Jekyll will parse any file with front matter at the very beginning of the file. Empty front matter looks like so:

```
   ---
   ---
```

You can also include the following variables:

| Variable | Description | Format |
|:---|:---|:---|
|layout:| Which template to choose in _layouts. |`default`, `page`, `post`|
|title:| Text which shows in the webpage title and also the jumbotron |\<string\>|
|date:| Used to sort a `post` in chronological order. Also used in feed.xml. | YYYY-MM-DD HH:MM:SS +/-TTTT |
|category:| What category your `post` belongs in. |\<string\>|
|categories:| What categories your `post` belongs in. |[\<string\>, ...]|
|tags:| A list of tags relevant to the `post`. |[\<string\>, ...]|
|excerpt:| Text which shows in the page meta description. If used in a `post` it will act as the synopsis on the front page. |\<string\>|
|subtitle:| Text which shows under the title in the jumbotron. |\<string\>|
|menu:| Which navbar item is to have the class `selected` |\<string\>|
|toc:| Whether this page should have an auto-generated table of contents. | `true` \| `false`|
|geopattern:| A custom string input for the jumbotron SVG background. Otherwise it uses `title:` |\<string\>|
|navbar:| Used to override the navbar style for this page. | navbar-inverse navbar-inversed |
|css:| Custom CSS to include on this page. Must install to `/assets/css/` but only list the filename. |[\<string\>, ...]|
|js:| Custom JS to include on this page. Must install to `/assets/js/` but only list the filename. |[\<string\>, ...]|

A common example of front matter for a `post` would be

```
---
layout: post
title:  "Example Post"
date:   2017-05-10 13:25:35 +0200
categories: nifskope releases
---

```

Using `jekyll-admin` will automate most of this for you, and you can include custom front matter variables in the field below the post text. 
