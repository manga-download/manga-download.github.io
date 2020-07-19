---
title: "Manga & Anime Downloader "
layout: splash
permalink: /
date: 2020-07-19
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/banner.png
  actions:
    - label: '<img alt="Download Stable" src="https://img.shields.io/github/downloads/manga-download/hakuneko/latest/total?label=Download%20-%20HakuNeko%20%28Stable%29&logo=github"/>'
      url: "https://github.com/manga-download/hakuneko/releases/latest"
    - label: '<img alt="Download Nightly" src="https://img.shields.io/github/downloads-pre/manga-download/hakuneko/latest/total?color=blue&label=Download%20-%20HakuNeko%20%28Nightly%29&logo=azure-devops"/>'
      url: "https://github.com/manga-download/hakuneko/releases"
    - label: '<img alt="Discord" src="/assets/images/discord-small.png" /> Join us on Discord'
      url: "https://discord.gg/A5d3NDf"
  caption: "HakuNeko's interface"
excerpt: "With HakuNeko, find your favorite manga or anime from your usual websites (AKA connectors) and start downloading or simply view the content."
intro: 
  - excerpt: "HakuNeko is a cross-platform downloader for manga and anime from various websites. HakuNeko was made to help users who download media for circumstances that requires offline usage. The philosophy is ad-hoc consumption, get it when you want to read/watch it. It is not meant to be a mass downloader to stock up thousands of chapters that are just collected and will probably never be read."
feature_row:
  - image_path: assets/images/splash-th-connectors.png
    image_caption: "Connectors"
    alt: "Connectors preview"
    title: "600+ sources"
    excerpt: "600+ websites which host the content are included as **Connectors**. HakuNeko does not host anything by itself."
    url: "https://github.com/manga-download/hakuneko/tree/master/src/web/mjs/connectors"
    btn_label: "List of Connectors"
    btn_class: "btn--primary"
  - image_path: /assets/images/splash-th-downloads.png
    image_caption: "Downloads"
    alt: "Downloads preview"
    title: "Download with a click"
    excerpt: "Simply find your manga and click on the download button to retrieve its content to your drive."
    url: "https://github.com/manga-download/hakuneko/wiki/Quick-Reference#download-queue"
    btn_label: "Download Queues"
    btn_class: "btn--primary"
  - image_path: /assets/images/splash-th-multilang.png
    image_caption: "Languages"
    alt: "Multi Languages"
    title: "Multi Language Support"
    excerpt: "Find connectors dedicated to your own language. Or simply discover connectors having multi languages."
    url: "https://github.com/manga-download/hakuneko/wiki/Quick-Reference#chapter-list"
    btn_label: "Chapter filters"
    btn_class: "btn--primary"
feature_row2:
  - image_path: /assets/images/splash-th-manga-anime.png
    image_caption: "Preview"
    alt: "Mangas and Animes"
    title: "Mangas, Animes and more ..."
    excerpt: 'Various content for various tastes ! HakuNeko allows you to enjoy your content in any format. If you want more, you can always ask for a new connector or feature (but be warned of the long list already waiting).<br/>You can also export to pdf or to ebook formats or use advanced *post scripts* to do whatever you want.'
    url: "https://github.com/manga-download/hakuneko/wiki/Quick-Reference#preview-panel"
    btn_label: "Content preview"
    btn_class: "btn--primary"
feature_row3:
  - image_path: /assets/images/splash-th-code.png
    image_caption: "Code editor"
    alt: "Code editor"
    title: "Open Source"
    excerpt: "Join the contributors and help us improve HakuNeko. You will find detailled guides on the github and a friendly developers community on discord to get some help.<br/>Start with a Pull Request and kindly ask for a review."
    url: "https://github.com/manga-download/hakuneko/wiki/Developer-Manual"
    btn_label: "Developers Guides"
    btn_class: "btn--warning"
feature_row4:
  - image_path: /assets/images/splash-th-interface.png
    image_caption: "HakuNeko"
    alt: "HakuNeko"
    title: "HakuNeko"
    excerpt: 'Download HakuNeko and start digging into the advanced features you want to use. Make sure that you read the documentation to learn how it works.'
    url: "https://hakuneko.download/"
    btn_label: "Download"
    btn_class: "btn--success"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="right" %}

{% include feature_row id="feature_row4" type="center" %}
