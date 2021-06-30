---
layout: post
title: "Division?"
author: DoubleCookies
---
*Just another math stuff:*

{% highlight javascript %}
let a = 0;

a += !(a[a]/a[a]==a[a]/a[a]) // a = 1
{% endhighlight %}

<!--more-->
### Explanation
- We are trying to use number as an array. *Nothing good will happen this way*.
- `a[a]` will return `undefined` and `a[a]/a[a]` will return NaN (it is definitely not a number!)
- Comparing NaN with NaN will return `false` and after inversion it will be `true`. After that — we add 1 to variable.