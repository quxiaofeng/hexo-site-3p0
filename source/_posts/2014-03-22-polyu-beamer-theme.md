---
layout: photo
title: "PolyU Beamer Theme"
description:
headline:
category: latex
tags: [latex, beamer, presentation, writing, PolyU]
comments: true
mathjax: false
date: 2014-03-22 16:05:03
photos:
- http://i.imgur.com/j1Nl1FR.png
- http://i.imgur.com/4OGjxSA.jpg
- http://i.imgur.com/n9luJJI.jpg
---

A polyu Beamer template

<!--more-->

## GitHub Repo

[https://github.com/quxiaofeng/PolyU_thesis_template](https://github.com/quxiaofeng/PolyU_thesis_template)

## About This Theme

This a beamer theme created for The Hong Kong Polytechnic University.

## Dependencies

1. Need Beamer (of course)
2. Need picins package in


    \texmf-local\tex\latex\local\



### Settings

    \usepackage[
        compress,
        %minimal,
        %nonav,
        red,
        %gold,
        %blue,
        numbers,
        %nologo,
        polyu,
        %comp,
        %forty,
        %seventyfive,
    ]
    {beamerthemeHongKong}

+ "compress" option is recommended. It provides a short header and information about slides structure.
+ "minimal" option provides a simplest framework.
+ "nonav" can suppress the navigating buttons on lower right-hand corner.
+ "red" option is the default and the only implemented color option.
+ "gold" option is not ready. It is inspired by the 75th anniversary ceremony. The link to the guidelines are found but dead. I am trying to get the access.
+ "blue" option is ready. It is inspired by the Computing Department 45th anniversary logo.
+ "numbers" option is the page number on the bottom left-hand corner.
+ "nologo" option enables the solo usage of color theme without PolyU logos on title page and headers.
+ "polyu" option is default option and it enables whether it exist or not.
+ "comp" option is to include the computing logo in the title page and the head banner.
+ "forty" option is to use the Computing Department 40th anniversary logo in the title page and the head banner.
+ "seventyfive" option is to use the PolyU 75th anniversary logo in the title page and the head banner.


## Template

+ CTeX suite was the design target, and CJK is used for the Chinese support.
+ Now it will change to be compiled with texlive 2012 or above.

## About the design

### Layout

The layout of this theme is based on the work done by [Jorg Cassens](http://cassens.org/) and [Till Tantau](http://www.tcs.uni-luebeck.de/mitarbeiter/tantau/) as shown in themes/theme/beamerthemeHongKong.sty.

This PolyU theme is a modification of the [NTNU Beamer theme](http://story.idi.ntnu.no/~cassens/blog/archives/39-A-Beamer-theme-for-NTNU.html). The general layout is same. The only differences are the color set and logos.

The aim of this modification is to create a nice and tidy PolyU theme using NTNU or the shadow style.

### Color

+ The majority of colors are various kinds of deep and light brick red.
+ The RGB values are extracted from PolyU official website before. Though I asked computing office for these files, I got nothing.
+ Now PolyU VI standard is found, but only a little is added into this theme. More needs to be done.
  1. Update color values according to the [PolyU VI](http://www.polyu.edu.hk/cpa/polyu/index.php?option=com_content&view=article&id=156&Itemid=48).
  2. Check PolyU standard PPT template. Though the whole design will maintain, defects and false usage of polyu elements should be fixed.

<figure>
  <img src="http://i.imgur.com/j1Nl1FR.png">
  <figcaption>
  The traditional PolyU theme with the red color and the polyu logo
  </figcaption>
</figure>



## COMP 40 Anniversary Theme `comp` and `forty`

The new banners and logos

<figure>
  <img src="http://i.imgur.com/RwKwlNG.jpg">
  <figcaption>
  New cmputing logo
  </figcaption>
</figure>

<figure>
  <img src="http://i.imgur.com/NlTejiH.jpg">
  <figcaption>
  Computing 40th anniversary logo
  </figcaption>
</figure>

And new color called `blue`

+ polyublue `(0, 140, 215) #008C7D`.
+ polyugreen `(143, 195,32) #8FC320`.
+ polyuicyblue`(83, 195,241) #53C3F1`.

#### `comp` and `blue` ####

<figure>
  <img src="http://i.imgur.com/4OGjxSA.jpg">
  <figcaption>
  An example with comp logo and blue color
  </figcaption>
</figure>

#### `forty` and `blue` ####

<figure>
  <img src="http://i.imgur.com/f4fARax.jpg">
  <figcaption>
  An example with the forty logo and the blue color
  </figcaption>
</figure>

#### `polyu`, `forty` and `blue` ####

<figure>
  <img src="http://i.imgur.com/AqpXt7C.jpg">
  <figcaption>
  An example with both the forty and the polyu logos and the blue color
  </figcaption>
</figure>

#### `polyu`, `comp` and `red` ####

<figure>
  <img src="http://i.imgur.com/aPY8hKY.jpg">
  <figcaption>
  An example with both the comp and the polyu logos and the red color
  </figcaption>
</figure>

**Actually, there are may different combinations. Just have fun.**

## PolyU 75 Anniversary Theme `seventyfive` and `gold`

<figure>
  <img src="http://i.imgur.com/0zqAyWG.png">
  <figcaption>
  The PolyU 75th anniversary logo
  </figcaption>
</figure>

<figure>
  <img src="http://i.imgur.com/n9luJJI.jpg">
  <figcaption>
  An example with both the seventyfive logos and the gold color
  </figcaption>
</figure>

## TODO

1. <del>Update with PolyU VI</del>.
2. <del>Add a gold setting following [PolyU's 75th Anniversary](http://75.polyu.hk/) color style. found the guidelines link [https://www2.polyu.edu.hk/Script/staff/cpa/Staff/75th_Guidelines/](https://www2.polyu.edu.hk/Script/staff/cpa/Staff/75th_Guidelines/) in this page [http://www.polyu.edu.hk/cpa/75thanniversary/index.php?route=gallery/seventyfivethanniversaryidentity](http://www.polyu.edu.hk/cpa/75thanniversary/index.php?route=gallery/seventyfivethanniversaryidentity). Have to contact [ITS](http://www.polyu.edu.hk/~its/aboutits/aboutits_04.html). If this attempt failed, the logo was designed by Mr Freeman Lau Siu-hong. Try to [contact him](http://www.freemanlau.com/en/index.html).</del>
3. Fine tuning of the color and other config.

