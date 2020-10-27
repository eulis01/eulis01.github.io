---
layout: post
title:      "❗️Stuck Debbugging Shotgun❗️"
date:       2020-10-26 17:22:05 +0000
permalink:  stuck_debbugging_shotgun
---


Well i was stuck for a day or 2 debbugging some issues with my sinatra project where flash was not working and one of the view of the project would not load the navbar. I must say i had spended some time researching and trying to debug these issues. A least i read the docs for all this gem as well as looked/read around the repo of the gems i was using for help. Somehow i noted i was using the gem => Shotgun to start my WebApp. 
```
$ shotgun 
```
Well i must say after a while of reading the docs i came across the thin server Readme of course i could just run the local thin sever intead of the shotgun gem so i was reading the docs and found the command to execute and run the server the server. 
 To my surprise it all worked so something on the gem shotgun was not letting me load or set the proper session cookies to the web browser.

This is the commad to run the local thin server. I  also run with the optional --debug command so if any error are present they would be show in the terminal in details. 

```
$ bundle exec thin start --debug
```
them just navigate to on your web browser to localhost:3000.
and navigate test and debug your website.
thank for reading https://twitter.com/Eulis01
