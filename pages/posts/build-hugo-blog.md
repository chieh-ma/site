---
title: "搭建基于Hugo框架的博客网站"
date: 2022-04-14T13:25:09+08:00
draft: false
categories: ["网站"]
tags: ["website"]
---
## 文件树
```
D:\HUGO
├─bin
│      hugo.exe
│      LICENSE
│      README.md
│
└─sites
    └─site
        │  .gitignore
        │  .hugo_build.lock
        │  config.yml
        │  empty.bat
        │  generate.bat
        │  hugohelper.exe
        │  upload.bat
        │
        ├─archetypes
        │      default.md
        │
        ├─content
        │  │  about.md
        │  │  admin.md
        │  │  archive.md
        │  │  contact.md
        │  │  donate.md
        │  │  guestbook.md
        │  │  search.md
        │  │
        │  └─posts
        │          article-and-page.md
        │          build-hugo-blog.md
        │          build-website.md
        │          category-and-tag.md
        │          computer-essential-software.md
        │          github520-and-switchhosts.md
        │          hello-world.md
        │          image-hosting-service.md
        │          local-video-player.md
        │          microsoft-office-365-product-activation-failed.md
        │          website-monitor.md
        │          win-combination-shortcut-key.md
        │
        ├─data
        ├─layouts
        ├─resources
        │  └─_gen
        │      ├─assets
        │      └─images
        ├─static
        │  │  favicon.jpg
        │  │  README.md
        │  │
        │  └─images
        │          kmplayer.png
        │          potplayer.png
        │          vlc-media-player.png
        │
        └─themes
            └─PaperMod
                │  go.mod
                │  LICENSE
                │  README.md
                │  theme.toml
                │
                ├─.github
                │  │  PULL_REQUEST_TEMPLATE.md
                │  │  stale.yml
                │  │
                │  ├─ISSUE_TEMPLATE
                │  │      bug_report.md
                │  │      config.yml
                │  │      new-blank-issue.md
                │  │
                │  └─workflows
                │          build.yml
                │          gh-pages.yml
                │
                ├─assets
                │  ├─css
                │  │  ├─common
                │  │  │      404.css
                │  │  │      archive.css
                │  │  │      footer.css
                │  │  │      header.css
                │  │  │      main.css
                │  │  │      post-entry.css
                │  │  │      post-single.css
                │  │  │      profile-mode.css
                │  │  │      search.css
                │  │  │      terms.css
                │  │  │
                │  │  ├─core
                │  │  │      reset.css
                │  │  │      theme-vars.css
                │  │  │      zmedia.css
                │  │  │
                │  │  ├─extended
                │  │  │      blank.css
                │  │  │
                │  │  └─hljs
                │  │          an-old-hope.min.css
                │  │
                │  └─js
                │          fastsearch.js
                │          fuse.basic.min.js
                │          highlight.min.js
                │
                ├─i18n
                │      ar.yaml
                │      bg.yaml
                │      bn.yaml
                │      ca.yaml
                │      ckb.yaml
                │      da.yaml
                │      de.yaml
                │      en.yaml
                │      eo.yaml
                │      es.yaml
                │      fa.yaml
                │      fr.yaml
                │      he.yaml
                │      hi.yaml
                │      hu.yaml
                │      id.yaml
                │      it.yaml
                │      ja.yaml
                │      ko.yaml
                │      ku.yaml
                │      mn.yaml
                │      nl.yaml
                │      pl.yaml
                │      pt.yaml
                │      ru.yaml
                │      sv.yaml
                │      tr.yaml
                │      uk.yaml
                │      uz.yaml
                │      vi.yaml
                │      zh-tw.yaml
                │      zh.yaml
                │
                ├─images
                │      screenshot.png
                │      tn.png
                │
                └─layouts
                    │  404.html
                    │  robots.txt
                    │
                    ├─partials
                    │  │  anchored_headings.html
                    │  │  author.html
                    │  │  breadcrumbs.html
                    │  │  comments.html
                    │  │  cover.html
                    │  │  edit_post.html
                    │  │  extend_footer.html
                    │  │  extend_head.html
                    │  │  footer.html
                    │  │  head.html
                    │  │  header.html
                    │  │  home_info.html
                    │  │  index_profile.html
                    │  │  post_canonical.html
                    │  │  post_meta.html
                    │  │  post_nav_links.html
                    │  │  share_icons.html
                    │  │  social_icons.html
                    │  │  svg.html
                    │  │  toc.html
                    │  │  translation_list.html
                    │  │
                    │  └─templates
                    │          opengraph.html
                    │          schema_json.html
                    │          twitter_cards.html
                    │
                    ├─shortcodes
                    │      blockquote.html
                    │      collapse.html
                    │      figure.html
                    │      ltr.html
                    │      rawhtml.html
                    │      rtl.html
                    │
                    └─_default
                        │  archives.html
                        │  baseof.html
                        │  index.json
                        │  list.html
                        │  rss.xml
                        │  search.html
                        │  single.html
                        │  terms.html
                        │
                        └─_markup
                                render-image.html
```
## 清空远程仓库
```
D:
cd Hugo\sites\site
md delete
cd delete
git clone git@github.com:chieh-ma/site.git
cd site
git rm *
git add .
git commit -m "empty"
git push origin main
cd ../..
rd/s/q delete
```
## 生成本地文件
```
hugo
```
## 上传到远程仓库
```
D:
cd Hugo\sites\site
cd public
git init
git add .
git commit -m "update"
git remote add origin git@github.com:chieh-ma/site.git
git remote -v
git pull origin main --allow-unrelated-histories
git push origin main
cd ..
rd/s/q public
```
