---
permalink: /docs/interface/
title: "Interface Layout"
excerpt: "How to use HakuNeko."
last_modified_at: 2020-07-30
toc: true
---

![reference layout](/assets/images/documentation/reference-layout.png)

The basic user interface is divided into different panels, which are somewhat grouped by their corresponding functionality.

-   The top-left panel contains system controls. Currently there is only the menu button to open the [Settings](#settings) followed by the application title.
-   The [Manga List](#manga-list) shows all available mangas from different sources such as websites, bookmarks, clipboard, …​ Furthermore it provides a simple search to filter the list.
-   The [Chapter List](#chapter-list) shows all available chapters for the currently selected manga from the manga list. It also supports basic sorting and advanced filtering options.
-   The [Download Queue](#download-queue) panel shows the status and progress of all chapters that are currently downloading.
-   The [???](#preview-panel) can be used to show the pages of the currently selected manga chapter or play the video stream in case of a selected anime episode.

Settings
--------

![reference settings](/assets/images/documentation/reference-settings.png)

Open the settings with the corresponding menu button in the system control panel at the top left corner of the user interface.

-   At the top is the about section which contains information about this HakuNeko build and some self-explaining links.
-   The settings section contains various general setting that are applied to the application or to each website. A description for  each option can be found in the tooltip of its label.
-   The general settings are followed by additional settings which are specific to each system control or website (e.g. login data). A description for each option can be found in the tooltip of its label.
-   With the bookmark import it is possible to transfer favorites from FMD to HakuNeko. The database file `favorites.db` is located in the `works` sub-directory of FMD’s application folder. The import is incremental and will not delete your existing favorites, it will just add new ones. After the import is complete, read the report carefully to see which of your favorites failed. You may repeat the import whenever HakuNeko included support for websites that were not yet supported during the previous import. You may repeat the import whenever you added favorites in FMD.
-   Save and close the settings.
-   Discard and close the settings.

Source Selection
----------------

![reference websites](/assets/images/documentation/reference-websites.png)

The source selection list can be reached by the corresponding control ② in the [Manga List](#manga-list). Besides the website sources, there are certain sources with a special meaning.

### Bookmarks  
The bookmark source will show all your favorite mangas.

### Folder  
The folder source will show all offline mangas from a local directory.
The directory can be assigned through the [Settings](#settings).

-   The source list can be filtered by a given search pattern. The search pattern will apply to the name of the source and eventually its URL.
-   It is possible to search for all sources that contains a certain manga that matches the given search pattern. It is required to press the `Enter` key to update the list everytime you change the search pattern. The search will only be performed locally for sources that have already been synchronized, it will not perform an online search.
-   The source list can also be filtered by tags. Select or deselect the tags for which sources shall be shown. The source must contain all of the selected tags (AND).
-   This button will clear all filters and tags
-   The list showing all sources based on the configured filters. Each source has a tooltip providing additional information. Each top right corner contains a link that will open the website of the source. This is useful to investigate problems or bypass protections such as [CloudFlare, Captcha or even Account Login requirement](#Manual-Website-Interaction). Click a source to select  it and close the source list.

Manga List
----------

![reference mangas](/assets/images/documentation/reference-mangas.png)

This panel shows mangas from various sources such as (supported) websites, bookmarks, clipboard, …​

-   Use this button to load the manga links (e.g. <https://mangadex.org/title/31013/eleceed>) currently stored in the clipboard into the manga list. This is useful to quickly drop manga downloads into HakuNeko while browsing manga websites with your browser.
-   It is also possible to browse manga lists directly in HakuNeko. This control provides access to the [???](#source-selection) from which the mangas shall be shown. There are also some special sources which are discussed later.
-   If a website is selected as source, the mangas will be shown from a locally cached list. To update the list use this synchronize button. The button will change its appearance while synchronizing the local manga list with the website.
-   Enter a search pattern to filter the manga list. The search is case insensitive. The pattern requires at least 3 characters to perform a search (or 2 with non-latin characters).
-   With the bookmark button you can add or remove the selected manga from he manga list to the bookmark list.
-   The list of mangas that are shown for the selected source and filtered by the search pattern. Select a manga to load its chapters in the [Chapter List](#chapter-list).
-   The status bar may show an activity icon when the list is loading or synchronizing. It also shows the number of filtered mangas in the list and the total number of available mangas for the selected source.

Chapter List
------------

![reference chapters](/assets/images/documentation/reference-chapters.png)

The chapter list shows the chapters of the selected manga from the [Manga List](#manga-list).

-   Use the sort button to toggle between different ordering of the chapters. The options are original, ascending, descending.
-   The download all button will add all chapters that are currently shown in the list to the [Download Queue](#download-queue) manager. Chapters that are not shown in the list wil not be downloaded.
-   Choose a langauge to show only chapters of this selected language.
-   Show only chapters that matches a given search pattern. Regular expressions are also supported.
-   The list of chapters that are shown for the selected source and filtered by the language and search pattern.
-   Each chapter has some controls and a title. The download button will add the chapter to the downlod list and save it to the folder that is configured in the [???](#settings). The button has different appearances reflecting the current state. See the tooltip for additional information. The preview button will show the pages of the chapter in the [???](#preview-panel). The marker toggle button allows to mark a single chapter of the selected manga. This can be useful to keep track of your last read chapter. This feature does not work in offline mode.
-   The status bar may show an activity icon when the list is loading. It also shows the number of filtered chapters in the list and the total number of available chapters for the selected manga.

Preview Panel
-------------

![reference pages](/assets/images/documentation/reference-pages.png)

![reference anime](/assets/images/documentation/reference-anime.png)

Shows the pages or the video for the selected chapter in the [Chapter list](#chapter-list). Downloaded chapters are shown from the local folder, otherwise the content is streamed directly from the website.

Download Queue
--------------

![reference downloads](/assets/images/documentation/reference-downloads.png)

Whenever a chapter is downloaded, it will be added to the download queue. After completion the download job will be removed from the download queue.

-   The list of chapters that are downloading, queued or failed. Each entry shows the title of the source, the manga and the chapter.
-   The button reflects the current status of the download. See the tooltip for further details, especially useful to show the error when a download failed. Click on a failed download to add the chapter again to the download queue.
-   The progress bar roughly shows the percentage of the remaining data until the download is complete.
-   The toggle button to show or hide the download queue.
-   The status shows the number of downloads that are queued in the list.

Reader
------

![reference reader](/assets/images/documentation/reference-reader.png)

To open the reader just click any of the pages from the [???](#preview-panel). The reader will directly jump to the page that was clicked. The control panel is at the top right corner and will expand as soon as the cursor enters (hover).

-   The current name of the chapter.
-   Navigate to the chapter that is below the current chapter in the chapter list without leaving the reader.
-   Navigate to the chapter that is above the current chapter in the chapter list without leaving the reader.
-   Decrease the space between the pages. This is useful to remove the gap when reading webtoons.
-   Increase the space between the pages.
-   Increase the size of the pages.
-   Decrease the size of the pages.
-   Close the reader.
