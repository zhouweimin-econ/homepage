# 个人主页部署

目标网址：https://zhouweimin-econ.github.io/

此源码已配置为 GitHub Pages 用户主页（`baseurl: ""`）。必须配合以下仓库设置，不能只将修改上传到仍名为 `homepage` 的项目仓库。

1. 打开 GitHub 上的 `zhouweimin-econ/homepage` 仓库，在 **Settings → General → Repository name** 将仓库改名为 **zhouweimin-econ.github.io**。如果该名字已被占用，请先检查现有同名仓库，不要覆盖或删除它。
2. 将本地修改的 `_config.yml`、新增的 `homepage.html` 和此 `README.md` 提交到改名后的仓库，放在原有源码的根目录。
3. 在 **Settings → Pages → Build and deployment** 中选择 **Deploy from a branch**，选择实际存放网站源码的分支（例如 `master` 或 `main`），目录选择 **/(root)**，然后保存。
4. 等待 Pages 构建和部署成功，访问根网址，检查 Home、Research、Teaching，以及图片、样式和课程 PDF。发布可能需要约 10 分钟；若失败，查看仓库 Actions 中的构建日志。

`homepage.html` 会在新站生成 `/homepage/`，将旧首页地址跳转到根网址；它不负责旧 Research、Teaching 等深层链接的迁移。

本地下载的源码文件夹名称无需修改。修改本地文件不会自动更新 GitHub，也不会自动更改线上仓库名称。

官方说明：https://docs.github.com/en/pages/quickstart

---

# Bay

[![Version](https://img.shields.io/gem/v/bay_jekyll_theme)](https://rubygems.org/gems/bay_jekyll_theme)
[![Downloads](https://img.shields.io/gem/dt/bay_jekyll_theme)](https://rubygems.org/gems/bay_jekyll_theme)

Bay is a simple theme for Jekyll. [[view live]](https://eliottvincent.github.io/bay)

Inspired by [dangrover.com](http://dangrover.com/). Current theme used at [eliottvincent.com](http://eliottvincent.com/).

![](/screenshot.png)

### Installation


The easiest solution is to [fork this repo](https://github.com/eliottvincent/bay/fork).
If you want to start from a clean website, follow the steps bellow:

Create a new Jekyll website:
```
jekyll new mysite
```

Open `Gemfile` and replace the line:
```
gem "minima"
```
with:
```
gem "bay_jekyll_theme"
```

Open `_config.yml` and replace the line:
```
theme: minima
```
with:
```
theme: bay_jekyll_theme
```
or, for GitHub Pages:
```
remote_theme: eliottvincent/bay
```

Finally, install the dependencies:
```
bundle install
```

and build the website!
```
jekyll serve
```


The website will look somewhat empty at first. That's normal. Follow the next instructions to complete the header and footer components, and the home and blog pages.

### Header
Open the `_config.yml` file and add the following:
```yml
header:
  pages:
    - name: Home
      slug: /     # <-- index.md
    - name: Blog  # <-- blog.md
    - name: Whatever  # <-- whatever.md
```
Re-run `jekyll serve` to see the header updated.

### Footer
Open the `_config.yml` file and add the following:
```yml
footer:
  show_powered_by: true
  contact:
    - name: Email
      value: yourmail@domain.com
      link: mailto:yourmail@domain.com
    - name: WeChat
      value: YourWeChatUsername
      link: "#"
  follow:
    - name: Twitter
      link: http://twitter.com/YourTwitterUsername
      username: "@YourTwitterUsername"
    - name: Facebook
      link: http://facebook.com/YourFacebookUsername
    - name: LinkedIn
      link: http://linkedin.com/in/YourLinkedInUsername
    - name: GitHub
      link: http://github.com/YourGitHubUsername
    - name: Dribbble
      link: https://dribbble.com/YourDribbbleUsername
    - name: Weibo
      link: http://weibo.com/u/YourWeiboUsername
    - name: RSS
      link: /feed.xml
```
Re-run `jekyll serve` to see the footer updated.

### Home page
Create (or edit) the `index.markdown` file and add the following:
```yml
---
layout: home
profile_picture:
  src: /assets/img/profile-pic.jpg
  alt: website picture
---

<p>
  Welcome to mysite!
</p>
```

### Blog page
Create `blog.markdown` file and add the following:
```yml
---
layout: blog
title: Blog
slug: /blog
---

This is an example of a "Blog" page, displaying a list of posts.
<br />
```


Your website is ready!


### Development

#### Run development instance (with hot-reload)
```sh
bundle exec jekyll serve
```

#### Build and publish the gem
```sh
gem build bay_jekyll_theme.gemspec
```

```sh
gem push bay_jekyll_theme-1.x.x.gem
```
