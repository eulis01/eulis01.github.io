---
layout: post
title:      "❗️Stuck Debugging Shotgun ❗️"
date:       2020-10-26 13:22:05 -0400
permalink:  stuck_debbugging_shotgun
---


Well I was stuck for a day or 2 debugging an issue with my Sinatra project where flash was not working and one of the view of the project would not load the navbar. I must say I had spent some time researching and trying to debug. A least I read the docs for all this gem as well as looked around the repo of the gem I was user for help. Somehow I noted I was using the gem ⇒ Shotgun to start my app.
'''
$ shotgun
'''
Well I must say after a while of reading the docs I came across the thin server of course I could just run the local thin sever instead of the shotgun gem, so I was reading the docs and found the command to run the server.
And to my surprise it all worked so something on the gem shotgun was not sending a proper session cookies to the web browser.

This is the command to run the local thin server. I also run with the optional --debug command so if any error are present they would be shown in the terminal in details.

'''
$ bundle exec thin start --debug
'''
them just navigate to on your web browser to localhost:3000.
Thanks for reading!
