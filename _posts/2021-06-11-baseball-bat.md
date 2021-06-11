---
layout: post
title: "Baseball bat"
author: DoubleCookies
---
This is first time when variable name isn't `a`:

{% highlight javascript %}
let baseball_bat = 0;

baseball_bat += 0==[[[[[[]]]]]] // BONK! baseball_bat = 1
{% endhighlight %}

<!--more-->
### Explanation
Comparing 0 to this... *array* return 1. Let's figure it out step-by-step:
- In the beginning we are trying to compare Number with Object. 
You can find how it works in [specification](https://262.ecma-international.org/11.0/#sec-abstract-equality-comparison).
Array will be casted with `ToPrimitive()` operation and return `""`.
    - Result will be same for `[]`, `[[]]`, `[[[]]]`, etc.
- In result, we have `"" == 0`. Now we visit specification again and find out that we need transform string with
`ToNumber()` operation, and it will return 0.
- `0 == 0` will return `true`. In the end, adding `true` is similar to adding 1 (still not the best idea).    