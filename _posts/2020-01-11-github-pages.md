---
layout: post
title: 'GitHub pages'
categories: [github]
tags: [github pages, tech, web]
---

## Introduction

GitHub offers nice way to serve static web pages directly from GitHub repository to your own subdomain. It also can use Jekyll (with Liquid templating language) and you can write your web content in a nice markdown format: <https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>

You can either pick a ready made Jekyll theme or you can write your own styling. Here I go through how to start with the ready made themes. To setup this it takes less than 10 minutes.

If you want make folders to your GitHub page you must first clone your GitHub pages repository to your local machine, then do all these changes there and commit those changes to the `master` branch. To see your end result it usually takes couple minutes to propagate to the public webpage.

- Official GitHub pages info: <https://pages.github.com>
- Jekyll documentation: <https://jekyllrb.com/docs/github-pages>

## Instructions

- Create a repository to your GitHub named like this: `<your GitHub username>.github.io`. I have it like this `satak.github.io`: <https://github.com/Satak/satak.github.io>

- Go to repository settings and select a GitHub pages Theme that you like, this page uses the `minimal` theme
![GitHub Settings](/assets/github_settings.png)
![GitHub Pages Theme](/assets/github_pages_theme.png)
![GitHub Pages Theme](/assets/github_pages_theme_selection.png)

- Create `README.md` file to your GitHub repository root and add this content:

```markdown
# Blog posts
{% raw %}
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
{% endraw %}
```

- Create (if doesn't exist) `_config.yml` file to your GitHub repository root and add this content there:

```yaml
theme: jekyll-theme-minimal
author: <here put your own GitHub user name or your actual name or nick>
```

- Create `assets` folder to your GitHub repository root for your pictures and add a picture file there

- Create `_posts` folder to your GitHub repository and add markdown file there named like this: `2020-01-01-my-post.md` (date is automatically picked up for html rendering) and add some markdown content there:

```markdown
---
layout: post
title: 'My first blog posts'
categories: [test]
tags: [test, cats, dogs]
---

This is my first blog post!

### Sub title here

More text here with cat pictures from my repository

![Picture of my cute cat](/assets/cute_cat.png)
```

- Now your GitHub repository should look something like this:
![GitHub example](/assets/github_example.png)

- This is now all done and you should see your public GitHub webpage at `<yourname>.github.io` url address!

- You can also set your own custom domain to point to your github pages site:

<https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site>
