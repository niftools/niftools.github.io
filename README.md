# niftools.github.io


## Installing Locally

### Prerequisites

You need to install Ruby. After you install Ruby you can simply install Bundler:  `gem install bundler`

Then to get the necessary gems for the site you run `bundle install` from the project root.

You will most likely get an SSL error while trying to build so you need to grab [http://curl.haxx.se/ca/cacert.pem](http://curl.haxx.se/ca/cacert.pem) then install it anywhere (e.g. Ruby folder) and add it to your `PATH`.

`OPTIONAL` If you want to edit or create posts more easily (instead of by hand), you can uncomment `- jekyll-admin` in `_config.yml` to use the admin interface at localhost:4000/admin.  This change does **not** need to be committed as `jekyll-admin` is local only.  I would recommend leaving it otherwise commented as it appears to disable file watching while editing the site design.

`OPTIONAL` If you are ever designing new pages and need to change `\bower_components` in order to add package dependencies you will need to install Node.js/npm.  You must then install Bower with `npm install -g bower`.  From there you can add Bower packages to the project root's bower.json and then run `bower install` or you can run `bower install <package>`. 

### Building and Running

To build the site locally you run `jekyll build`.  To serve the site locally you can run `jekyll serve`.  This will serve from localhost:4000 and will watch for any changed files so that changes will show up as you make them.

To view what the site would look like with the posts in `_drafts` published you can run `jekyll serve --drafts`.


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

## Publishing

To avoid publishing manually, you may use `jekyll-admin` if you have uncommented it in `_config.yml` and restarted jekyll.  The admin interface will be available at localhost:4000/admin. You can include custom front matter variables in the field below the post text. 

### Posts

Placing any Markdown or HTML file in `_posts` with valid front matter will publish the file to the site.  Where it goes will depend on the front matter such as the layout and what categories are listed. A `post` layout with `categories: nifskope releases` will get published to `/nifskope/releases/`.

[Relevant Documentation](https://jekyllrb.com/docs/posts/)

#### Categories

Most posts should likely consist of two categories:  the project or main product name and a subcategory such as releases e.g. `categories: nifskope releases` or `categories: blender releases`.  If posting about general developmental news or about multiple projects, use something like `category: updates`. 

### Pages

A `page` layout titled `mypage.md` will get published to `/mypage` if it is in the project root. 

[Relevant Documentation](https://jekyllrb.com/docs/pages/)



