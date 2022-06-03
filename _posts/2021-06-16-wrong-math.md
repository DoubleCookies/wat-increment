---
layout: post
title: Wrong \"Math\"
author: DoubleCookies
---
Looks like today math wouldn't be on our side:

{% highlight javascript %}
let a = 0;

a += "-1" < "-2" // a = 1
{% endhighlight %}

<!--more-->
### Explanation
Actually, there is nothing wrong with math — we got this because of string compare:
- Strings in JS are compared character by character. If symbols codes are equal - next pair is selected 
(there are additional rules but now they won't help us).
- When we compare `"-1"` and `"-2"` comparator skips first symbol and compare `'1'` with `'2'`. Of course `'1'` is less than `'2'`.
- In result, it will return `true` which is equal to `1` when we add it to variable.
- Done!