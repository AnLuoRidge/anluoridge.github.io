---
title: "Hugo"
date: 2022-07-10T21:38:46+10:00
draft: true
---

New a post: `cd ~/blog && hugo new post/my-first-post.md` (Use `post` because of theme Even)

To generate the site: `hugo --cleanDestinationDir`.

Then `cd pubic`,  git commit , push

## Changes I made

`layouts/_defaults/baseof.html`
added  `<meta name="google-site-verification" content="Yss2vcvnuYk7ODhz3_GlWugMapiFYe56Vy-KhY4uMwU" />`
https://github.com/olOwOlo/hugo-theme-even/pull/405/files


TODO
- [ ] 换个主题，现在的标题不够突出，字体我也不喜欢。Hello Friend。
- [ ] Check Google Index
- [ ] [hello-friend | Hugo Themes](https://themes.gohugo.io/themes/hugo-theme-hello-friend/)
- [ ] Improve google site verification
- [ ] Comment feature
- [ ] A better theme
- [ ] Integrate with Obsidian
- [ ] Enable GitHub Actions
- [ ] [Hello Hugo :: 木木木木木](https://immmmm.com/hello-hugo/)
- [ ] [Add a Random Page Button to Hugo Site - DEV Community](https://dev.to/idontremember/add-a-random-page-button-to-hugo-site-45e9)
- [ ] [shuffle | Hugo](https://gohugo.io/functions/shuffle/)




Even's archtypes

```
# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

# You can enable or disable out-of-date content warning for individual post.
# Comment this out to use the global config.
#enableOutdatedInfoWarning: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

```


[Is it possible to pass custom frontmatter parameters through "hugo new" CLI command? - support - HUGO](https://discourse.gohugo.io/t/is-it-possible-to-pass-custom-frontmatter-parameters-through-hugo-new-cli-command/31780)


```nginx
location / {
    try_files $uri $uri.html @rewrite;
}

location @rewrite {
    rewrite ^(.+)$ $1.html permanent;
}
```


The nginx config on Synology
>ssh into your NAS
sudo -i
cd /etc/nginx/conf.d/
ls -lia
cd to what should be the only GUID directory, e.g.:
cd 59bad806-9491-4fe1-a183-874d2f814633/
vim user.conf
Add headers, e.g.:
add_header X-DNS-Prefetch-Control On;
add_header X-Frame-Options DENY;
add_header X-Content-Type-Options nosniff;
add_header X-XSS-Protection "1; mode=block";
add_header Referrer-Policy no-referrer;
add_header Expect-CT "…";
add_header Feature-Policy "…";
add_header Content-Security-Policy "…";
:x! to save user.conf
nginx -s reload && nginx -t



