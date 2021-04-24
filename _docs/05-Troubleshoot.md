---
permalink: /docs/troubleshoot/
title: "Troubleshooting"
excerpt: "What to do in case of errors"
last_modified_at: 2021-04-24
toc: true
---

Any problems when using HakuNeko?
Please check these things first before [submitting an issue on github](https://github.com/manga-download/hakuneko/issues/new/choose).

Are you using the latest desktop client?
----------------------------------------

Only the latest desktop client will be maintained. Older desktop clients may not work properly because of the constantly updates of the manga websites.

Are you using the correct desktop client?
-----------------------------------------

Make sure the desktop client you use is compatible with your operating system and architecture (32bit, 64bit).

Is the Screen Blank/Black when starting HakuNeko?
----------------------------------------

*First make sure you are using version 6.1.7 or above, the update servers for older versions of HakuNeko no longer exist and therefore cannot initialize the user interface!*

However, even for recent versions this seems to be a common problem and the cause is unknown.
The issue is already tracked in [#13](https://github.com/manga-download/hakuneko/issues/13).
What you can do is start the HakuNeko application from terminal and check the output for error messages (you may post it in issue #13 to help solving this problem).
Furthermore, when the blank/black window appears, press `F12` to open the developer tools.
Check the console tab for any error messages (again you may post it in issue #13).
What else can you do?
Run your HakuNeko executable with the `--disable-gpu` parameter (per terminal or by adding it to the application shortcut), electron still seems to have graphic driver issues on some systems.
Check if your Antivirus is blocking HakuNeko for some reason.
Make sure you can reach the GitHub website, because HakuNeko checks GitHub for updates.
Restart HakuNeko multiple times (but give it some time, HakuNeko may update which consists of 1100 files).
Try to delete the [Cache Directory](/docs/install/#cache) and start HakuNeko again.
As a last resort, you can patch HakuNeko manually as described below:

* Go to [https://github.com/manga-download/hakuneko/tree/gh-pages](https://github.com/manga-download/hakuneko/tree/gh-pages)
* Change into the directory that matches your HakuNeko version (e.g. `6.1.7`)
* Download the `zip` archive that is inside the folder
* Now open your HakuNeko cache directory and delete all files and folders inside that directory
* Extract the content of the downloaded archive into the clean cache directory
* Create an additional file and name it `version` without any file extension
* Open this `version` file with notepad, fill in the name of the downloaded `zip` archive without the extension (e.g. `K65HGPDC`) and save the file
* Now start HakuNeko and see if it works

There is a possibility that automatic updates did not work for you (the blank/black screen may be an indicator for this).
In this case you have to repeat this procedure from time to time to stay up-to-date.

Is the manga website working in your Browser?
---------------------------------------------

When a manga or chapter does not work as expected please CHECK THE WEBSITE directly from within your web-browser. HakuNeko is only expected to show what is also provided for you on the website that hosts the mangas.

Are chapters or pages not shown (empty list)?
---------------------------------------------

This could be a problem with HakuNeko, but first make sure the manga, chapter and pages are accessible on the website from within your web-browser. There is a chance that the website is offline, the content requires to be purchased, or the manga you tried to access is blocked for your country. HakuNeko can not show chapters or pages if they are not even accessible from within your browser.

Have you updated the mangalist?
-------------------------------

In some cases the links in the mangalist may change. So if chapters for mangas are blank, select the website for which you want to update the mangalist and press the small refresh button on the right. Check if the chapters are shown after the mangalist has been updated.

Are you using a Proxy Server?
------------------------------

Proxy rules can be configured in HakuNeko settings. This allows you to use a proxy server when accessing manga. If you have problems accessing certain website with HakuNeko try it again with/without proxy rules. Some websites may not like your IP (e.g. region ban), while others may not like the IP of the proxy server.

Is the download stuck?
----------------------

The download is stuck and all other downloads from the same website are queued and will not be processed. This problem is already known and there are plenty of threads in the forum. Currently the reason is unknown and there is no solution for this problem.
You may try to reduce the number of host connections in the settings to prevent to many concurrent requests.

Making an informative help request
----------------------------------

When nothing of these workarounds solve your problem, please ask for help, but provide useful information other than "download not working anymore". 
The following information is very welcome and may help to reproduce the problem faster:

- Whats your operating system?
- Which desktop client version are you using (e.g. 6.1.7)?
- What is the rev. number (e.g. 0c3bac, shown at the top right of HakuNeko's settings menu)?
- Which website / manga / chapter did not work (only if applicable)?
- Which settings have you set in HakuNeko that are related to your issue (especially Chapter Naming Format, Host Connections and Output File Format)
- What is shown in the error log after the problem occurs (press `F12` key and select the console tab)?
- What is not working for you that you expected to work.
