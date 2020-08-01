---
permalink: /documentation/
layout: single
title: "Documentation"
excerpt: "How to use HakuNeko."
last_modified_at: 2020-07-30
toc: true
---
Installation
============

Setup
-----

Download the correct installation package for your operating system from
the [releases](https://github.com/manga-download/hakuneko/releases/latest) page. Run the installer and follow the
instructions on the screen. Start the application by executing the
corresponding desktop shortcut or start menu entry.

Note: you can also download the [nightly](https://github.com/manga-download/hakuneko/releases) that is including all the freshest updates but could have issues as it is a "work in progress.

Portable
--------

A portable installation is only available for Windows. Download the
correct portable package for your operating system from the
[releases](https://github.com/manga-download/hakuneko/releases/latest) page. Extract the content from the archive to
any place you want (e.g. USB thumb drive). Start the application by
executing `hakuneko.exe` from the extracted folder.

Directories
===========

After the installation is complete HakuNeko’s content is stored in
different folders. The directories depends on the type of operating
system and the version type (installed/portable).

Application
-----------

This directory contains the desktop client that is merely a web-browser
based on the electron framework. Platform specific binaries are stored
within this directory.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Path</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Win Portable</p></td>
<td><p><code>./</code> (The folder where the user extracted the application)</p></td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td><p><code>%PROGRAMFILES%\HakuNeko Desktop</code></p></td>
</tr>
<tr class="odd">
<td><p>Linux</p></td>
<td><p><code>/usr/lib/hakuneko-desktop</code></p></td>
</tr>
<tr class="even">
<td><p>MacOS</p></td>
<td><p><code>Applications/HakuNeko Desktop.app</code></p></td>
</tr>
</tbody>
</table>

User Data
---------

This directory contains all configurations for hakuneko (e.g. settings,
bookmarks, manga lists, …​). Furthermore there are user based
configurations for the chrome engine. All configuration files for
hakuneko are prefixed with **hakuneko**.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Path</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Win Portable</p></td>
<td><p><code>./userdata</code></p></td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td><p><code>%USERPROFILE%\AppData\Roaming\hakuneko-desktop</code></p></td>
</tr>
<tr class="odd">
<td><p>Linux</p></td>
<td><p><code>~/.config/hakuneko-desktop</code></p></td>
</tr>
<tr class="even">
<td><p>MacOS</p></td>
<td><p><code>~/Library/Application Support/hakuneko-desktop</code></p></td>
</tr>
</tbody>
</table>

User Plugins
------------

All user specific third party plugins (website scrapers) can be placed
in this plugin directory. Plugins must be a module which is compatible
with the
[Connector](https://github.com/manga-download/hakuneko/wiki/Developer-Website-Tutorial#the-website-scraper-structure)
interface. Plugins must have the `.mjs` file extension. Plugins can be
disabled by adding a dot `.` in front of the filename.

    import Connector from 'hakuneko://cache/mjs/engine/Connector.mjs';
    import Manga from 'hakuneko://cache/mjs/engine/Manga.mjs';

    /**
     * Author: ???
     * Date: ???
     * URL: https://github.com/???
     *
     * Installation:
     *   Place all files into your plugin directory
     *   => https://github.com/manga-download/hakuneko/wiki/User-Manual#directories
     */
    export default class HelloPlugin extends Connector {

        constructor() {
            super();
            super.id = 'helloplugin';
            super.label = 'Hello Plugin';
            this.tags = [];
            this.url = 'https://www.epikmanga.com';
        }

        // Replace the default icon by simply link an existing or your own icon file
        get icon() {
            //return 'hakuneko://cache/img/connectors/crunchymanga';
            return 'hakuneko://plugins/HelloPlugin.png';
        }

        /*
        // Replace the default initialization (rarely required)
        async _initializeConnector() {
            return Promise.resolve();
        }
        */

        // Provide copy & paste support by creating a manga from scraping the given link
        async _getMangaFromURI(uri) {
            return new Manga(this, uri.pathname, 'Manga 001');
        }

        // Get the manga list
        async _getMangaList(callback) {
            let mangaList = [
                {
                    id: 'dragonball',
                    title: 'Plugin: Dragonball'
                },
                {
                    id: 'onepiece',
                    title: 'Plugin: One Piece'
                }
            ];
            callback( null, mangaList );
        }

        // Get the chapter list for a given manga
        async _getChapterList(manga, callback) {
            let chapterList = [
                {
                    id: manga.id + '/ch1',
                    title: manga.title + ' - Chapter 001'
                },
                {
                    id: manga.id + '/ch2',
                    title: manga.title + ' - Chapter 002'
                }
            ];
            callback(null, chapterList);
        }

        // Get the image links for a given manga/chapter
        async _getPageList(manga, chapter, callback) {
            let pageList = [
                'https://www.epikmanga.com/upload/manga/god-of-martial-arts/1.1/02.jpg',
                'https://www.epikmanga.com/upload/manga/god-of-martial-arts/1.1/04.jpg'
            ];
            callback(null, pageList);
        }
    }

Download Demo Plugin: [HelloPlugin.zip](https://github.com/manga-download/hakuneko/wiki/assets/HelloPlugin.zip)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Path</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Win Portable</p></td>
<td><p><code>./userdata/hakuneko.plugins</code></p></td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td><p><code>%USERPROFILE%\AppData\Roaming\hakuneko-desktop\hakuneko.plugins</code></p></td>
</tr>
<tr class="odd">
<td><p>Linux</p></td>
<td><p><code>~/.config/hakuneko-desktop/hakuneko.plugins</code></p></td>
</tr>
<tr class="even">
<td><p>MacOS</p></td>
<td><p><code>~/Library/Application Support/hakuneko-desktop/hakuneko.plugins</code></p></td>
</tr>
</tbody>
</table>

Cache
-----

This directory contains the pure web application and will be updated
automatically whenever a new version of the web application is available
on the server.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Path</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Win Portable</p></td>
<td><p><code>./cache</code></p></td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td><p><code>%USERPROFILE%\AppData\Local\hakuneko-desktop\cache</code></p></td>
</tr>
<tr class="odd">
<td><p>Linux</p></td>
<td><p><code>~/.cache/hakuneko-desktop</code></p></td>
</tr>
<tr class="even">
<td><p>MacOS</p></td>
<td><p><code>~/Library/Caches/hakuneko-desktop</code></p></td>
</tr>
</tbody>
</table>

Temp
----

This directory is used for temporary data such as extracted images from
CBZ or EPUB archives.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Path</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Win Portable</p></td>
<td><p><code>%TEMP%\hakuneko</code></p></td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td><p><code>%TEMP%\hakuneko</code></p></td>
</tr>
<tr class="odd">
<td><p>Linux</p></td>
<td><p><code>/tmp/hakuneko</code></p></td>
</tr>
<tr class="even">
<td><p>MacOS</p></td>
<td><p><code>$TMPDIR/hakuneko</code></p></td>
</tr>
</tbody>
</table>
