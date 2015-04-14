title: Hexo Generated Blog 
date: 2014-05-14 02:43:54
tags: [blog, website, jekyll, hexo]
category: coding
---

Migrant the blog to [hexo](http://hexo.io/).

<!--more-->

I have been insterested in [`hexo`](http://hexo.io/) for over a year. And finally I got [this site](http://quxiaofeng.me) generated.

The concerns that delayed my decision are as follows:

1. The [hexo](http://hexo.io/) site is generated in local. The site has to be uploaded after being generated.

2. The source and the public site are actually two different git repos.

The final kick is the astonishing slow and pretty theme [Phase](http://zespia.tw/blog/2012/12/07/hexo-theme-phase/). At first, I just want to try and test this theme. I migranted previous jekyll-style markdown files to a [Phase](http://zespia.tw/blog/2012/12/07/hexo-theme-phase/)-themed hexo site. Though the theme is slow in some PCs or browsers, the migrant process is pretty smooth. [The themes](https://github.com/tommy351/hexo/wiki/Themes) are actually abundent comparing with [jekyll themes](http://jekyllthemes.org/). Then, I continued the migrant and finished it.

---

This site is generated in a Ubuntu 14.04. All tools are installed with npm. The dependencies are [`Node.js`](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager), [`hexo`](http://hexo.io/docs/index.html), [`hexo-math`](http://catx.me/2014/03/09/hexo-mathjax-plugin/) and [`cover` theme](https://github.com/daisygao/hexo-themes-cover).

---

I did a little fix to the [`cover` theme](https://github.com/daisygao/hexo-themes-cover).

1. The [duoshuo fix](https://github.com/quxiaofeng/hexo-themes-cover/commit/8e9ac9dd1748fad96af2ec260b6994fde0c438c7#diff-9f6b1a858766407dc868689e3495f0de).

I don't know why previous setting is not working. Therefore, I rewrite it as it is now.

2. The [addthis/jiathis fix](https://github.com/quxiaofeng/hexo-themes-cover/commit/8e9ac9dd1748fad96af2ec260b6994fde0c438c7#diff-9f6b1a858766407dc868689e3495f0de) 

In Gao's [`cover` theme](https://github.com/daisygao/hexo-themes-cover), the jiathis uid is not exposed in {% raw %}`_config.yml`{% endraw %}. Now it is in `theme.addthis.uid`.

And also a page switch `page.share` is added. This `addthis` share can be disabled by setting `share: false`.

3. Add multiple icons for the site

This idea is inspired by the [jekyll HMFAYSAL OMEGA theme](http://jekyllthemes.org/themes/hmfaysal-omega-theme/). Many icons are added to the site header file. It shows proper icons in different Apple devices.

---

For now, I host [the public site](https://github.com/quxiaofeng/quxiaofeng.github.io) and [the modified theme](https://github.com/quxiaofeng/hexo-themes-cover) in Github. The [source of the site](https://bitbucket.org/quxiaofeng/hexo-migrant) is hosted in bitbucket as a private repo.

---

## My favourate feature:

1. Automatic deploying to github. The whole deploy process is done automatically after generating. It is also convinient to change to a different repo. I always test on site, not local, because it is actually very different in local. Even you are sure it is fine in local, it still goes wrong in github. I love this feature.
2. Gallery (`layout: photo` and `photos: -img1 -img2`) page support.
3. Changing different theme is easy and independent to the content. All themes are stored in the `themes/themename`. When using jekyll, changing themes means manually replace all files, images, independent pages and other configure.
4. Chinese resources are abundent. The inventor and many users of hexo are Chinese. Therefore, many problems have already been solved.
5. The source and the public are stored in separate repos. The good part is that it protect your source. The bad part of it is that you can not learn from others.
6. Fancy box (Image gallery in page) support, MathJax (latex equation) support, Jiathis (social share) support, and Duoshuo (social comments) support.

---

The fine tuning of this site will be on-going for a while. As for now, I am pretty satisfied.