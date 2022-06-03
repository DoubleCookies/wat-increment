---
layout: post
title: 🤣 😂
author: DoubleCookies
---
Emojis in code? Why not?

{% highlight javascript %}
let a = 0;

a += '🤣'.charCodeAt(0)-'😂'.charCodeAt(0) // a = 1
{% endhighlight %}

<!--more-->
### Explanation
- First of all, **emojis are different to normal text**. Emojis UTF-16 encoding is greater than 16 bits, so `"😀".length` 
will return **2** (and `"😀".split('')` will return 2 symbols).
- In the code above we just get codes of first emojis symbols (55358 and 55357).

PS. `codePointAt` method is preferable for handling emojis (instead of `charCodeAt`). 