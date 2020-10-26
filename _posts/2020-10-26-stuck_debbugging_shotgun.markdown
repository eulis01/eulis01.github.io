---
layout: post
title:      "❗️Stuck Debbugging Shotgun❗️"
date:       2020-10-26 17:22:05 +0000
permalink:  stuck_debbugging_shotgun
---


Well i was stuck for a day or 2 debbugging an issue with my sinatra project where flash was not working and one of the view of the project would not load the navbar. i must say i had spended some time researching and trying to debug.  a least i read the docs for all this gem as well as looked around the repo of the gem i was user for help. somehow i noted i was using the gem => Shotgun to start my app. 
```
$ shotgun 
```
Well i must say after a while of reading the docs i came across the thin server of course i could just run the local thin sever intead of the shotgun gem so i was reading the docs and found the command to run the server. 
and to my surprise it all worked so something on the gem shotgunt was not seding a proper session cookies to the web browser.

This is the commad to run the local thin server. I  also run with the optional --debug command so if any error are present they would be show in the terminal in details. 

```
$ bundle exec thin start --debug
```
them just navigate to on your web browser to localhost:3000. 
thank for reading 
