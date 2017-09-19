
## NOTE

### Add new categories

1. go to directory category/
2. copy a template html to create a new html page for your new directory
3. edit your new html page, line 10 update
```
{% if post.main-class == 'crime' %}
```

## Basic Setup

1. [Install Jekyll](http://jekyllrb.com) (use the command ```sudo gem install jekyll```)
2. Fork this repo
3. Clone the repo you just forked.
5. Check out the sample posts in `_posts` to see examples for assigning categories and tags, and other YAML data.
7. **Remember to compile your assets files with Gulp.**

## Creating new page

You can use the `initpost.sh` to create your new posts. Just follow the command:

```
./initpost.sh -c Post Title
```

The new file will be created at `_posts` with this format `date-title.md`.

## Front-matter

When you create a new post, you need to fill the post information in the front-matter, follow this example:

```
---
layout: post
title: "Falando sobre RSCSS"
date: 2016-02-07 18:48:16
image: '/assets/img/rscss/rscss.png'
description: 'Escrevendo CSS sem perder a sanidade. Aprenda uma metodologia que pode salvar muitas dores de cabeça.'
main-class: 'css'
color: '#2DA0C3'
tags:
- css
- metodologia
- frontend
categories:
twitter_text: 'Escrevendo CSS sem perder a sanidade.'
introduction: 'Escrevendo CSS sem perder a sanidade. Com essa introdução, Rico St. Cruz o criador chama a atenção de todos sobre uma metodologia melhor para se escrever CSS.'
---
```

## Running the blog in local

In order to compile the assets and run Jekyll on local you need to follow those steps:

- Install [NodeJS](https://nodejs.org/) (remember to use the latest version)
- Run `sudo npm install`
- Run `sudo npm install -g gulp gulp-cli`
- Run `sudo gulp`


## License

This theme is free and open source software, distributed under the The MIT License. So feel free to use this Jekyll theme on your site without linking back to me or using a disclaimer.

If you’d like to give me credit somewhere on your blog or tweet a shout out to [@willian_justen](https://twitter.com/willian_justen), that would be pretty sweet.
