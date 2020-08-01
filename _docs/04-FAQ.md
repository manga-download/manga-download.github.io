---
permalink: /docs/FAQ/
title: "FAQ"
excerpt: "List of frequent use-cases"
last_modified_at: 2020-07-30
toc: true
---
Android or iOS
=============

**Can HakuNeko run on Android or iOS?**::
No, HakuNeko is build on [electron](https://electronjs.org) and therefore can only run on platforms that are supported by [electron](https://electronjs.org). Furthermore the current user interface is not optimized for mobile devices.

Image format
============

**Why are images downloaded in `.webp` format instead of `.jpg` or `.png`?**::
Images are always downloaded in the same format as they are available on the website to provide the best quality.
However, there are two exceptions where HakuNeko must re-compress images. Some websites are only providing scrambled/puzzled images as some kind of anti-scraping security mechanism. HakuNeko will de-scramble these images and save them in the format configured in the settings. The second case is when the chapters are downloaded as `PDF`, but the format is not compatible (e.g. `.webp`), HakuNeko will convert these images to `.jpg` with a quality of `90` before they are embedded into the output `PDF` file.
Furthermore, it is possible to use the `Post Command` in HakuNeko's settings to convert images after the download into another format. Read the tool-tip of the `Post Command` for some samples, or ImageMagick's documentation on how to use the command line `convert` tool.

Convert images
==============

**How to convert images after download?**::
Either use a third party tool to batch convert the images, or use HakuNeko's ability to run a `Post Command`:
On Linux or macOS make sure ImageMagick is installed and added to the PATH environment variable.
On Windows HakuNeko comes already bundled with ImageMagick, so no need for an additional installation.
. Open HakuNeko settings
. Find the setting for `Post Command`
. Enter the following command (example for Windows, Linux/macOS needs to be adjusted):
`mkdir "%PATH%_conv" 2>nul & convert "%PATH%\*.webp" -scene 1 "%PATH%_conv\%03d.png"`
  * Creates a new chapter folder with the suffix `_conv`
  * Process all images from the original chapter folder that matches `*.webp`
  * Images will be converted to PNG using 3-digit numbering starting with an offset of 1
  * The PNG images are stored in the new folder with the `_conv` suffix

Kindle
======

**How to convert EPUB to MOBI for Kindle?**::
Either use a third party tool to batch convert the ebooks, or use HakuNeko's ability to run a `Post Command`:
The kindle converter is bundled with all versions of HakuNeko, so no need for an additional installation.
. Open HakuNeko settings
. Find the setting for `Post Command`
. Enter the following command:
`kindlegen "%PATH%"`
  - Converts the EPUB file into a MOBI file (same manga directory)
  - This will only work if the EPUB is compatible (e.g. no webp images)

Missing Manga
=============

**Why are new mangas shown on the website, but not in HakuNeko's manga list?**::
HakuNeko is using a CDN to cache manga lists for certain websites to protect users from being IP banned for making to many requests. Unfortunately the CDN needs to be updated manually right now, so it can take 2~6 weeks until the list is updated. However users can still use the [Link Copy & Paste feature](https://github.com/manga-download/hakuneko/wiki/Quick-Reference#4-manga-list) to access the latest mangas within HakuNeko, even if they are not in HakuNeko's list. Cached lists can be found in the corresponding [repository](https://github.com/manga-download/hakuneko-cdn).

Copy and paste
==============
**How to use the Copy & Paste Feature?**::
Go to the website containing the manga you want to download.
Browse to the manga (the page that lists the chapters).
Copy the URL.
Switch to HakuNeko and press the paste button at top of the [manga list](/docs/interface/#manga-list) panel.

Download with failures
======================

**How to download chapters with broken images?**::
It is not possible. A chapter is broken if one or more of its images are broken. There are recurrent requests from users to allow downloading broken chapters, but for now this will not be supported for the following reason: Other users will start complaining why images are missing in some chapters.
Here are some recommendations to handle this problem:
* Report the chapter with the broken image to the website owner (but don't mention that you want to scrape with HakuNeko)
* Simply download the chapter from one of the other website sources (see watermark to find original scanlator website)