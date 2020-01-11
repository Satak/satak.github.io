---
layout: post
title: 'GitHub pages'
categories: [github]
tags: [github pages, tech, web]
---

GitHub offers nice way to serve static web pages directly from GitHub repository to your own subdomain. 

- Create a repository to your GitHub named like this: `<your GitHub username>.github.io`
- Go to repository settings and select a GitHub pages Theme that you like, this page uses `minimal` theme
![GitHub Settings](/assets/github_settings.png)
![GitHub Pages Theme](/assets/github_pages_theme.png)

- Create `README.md` file to your GitHub repository root and add this content:

```markdown
# Blog posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
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