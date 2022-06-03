---
layout: post
title: Reduce something
author: DoubleCookies
---
This getting out of hand. Now there are ~~two~~ three variables!

{% highlight javascript %}
let a = 0;

a = a + (""+(""+a[a])[2].charCodeAt()).split("").reduce((b,c) => +b + +c) // a = 1
{% endhighlight %}

<!--more-->
### Explanation
Let's start with `(""+(""+a[a])[2].charCodeAt())`:
- Here is old trick with `undefined` - we'll get it from `(a[a])`. After that we transform it to string. 
- In the next step, we will get the third letter - `"d"` - and its code (`100`). And again, transform it to string. 

So, `(""+(""+a[a])[2].charCodeAt())` will return `"100"`. It's time for split and reduce:
- Splitting string with empty separator will return every symbol as array element - `["1", "0", "0"]`.
- Finally, in reduce section, we transform all chars into numbers and add them to each other. 1 + 0 + 0 = 1.