---
title: MIME Types and GoDaddy
date: 2020-08-28
description: The little trick to get GoDaddy to serve json files.
tags: ['post', 'coding']
---
In my outside-of-work time, I help maintain a website for a non-profit. For a while it had been a Wordpress app,
but even with following small, regular updates of Wordpress, it no longer updated easily so I switched it to a
GatsbyJS site like this one. They only need a few pages so it didn't need the bulkiness of Wordpress.

When I went to put it on their servers, it mostly worked, except that some of the transitions like opening menu 
items didn't work. When I investigated that, it seemed that it wasn't able to find certain `.json` files. It turns out
that the Windows hosting on GoDaddy blocks `.json` files from being served unless you are specific about accepting them
in the `web.config` file. Store it at the root directory. It'll look something like this:

```
<configuration>
    <system.webServer>
        <staticContent>
            <mimeMap fileExtension=".json" mimeType="text/json" />
        </staticContent>
    </system.webServer>
</configuration>
```
