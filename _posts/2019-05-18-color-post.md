---
layout: post
title: Color Post
tags: [Test, Color]
color: brown
author: dshubitidze
excerpt_separator: <!--more-->
---

## How does it work?

Basically you need to add just one thing, the color:

```yml
---
layout: post
title: Color Post
color: brown
---
```

It can either be a html color like `brown` (which look like red to me). Or with the rgb:

```yml
---
layout: post
title: Color Post
color: rgb(165,42,42)
---
```

The background used is `lineart.png` you can edit it in the config file. 
If you want another one, put it in `/assets/img` as well. 

> ⚠️ It's a bit hacking the css in the `post.html`
