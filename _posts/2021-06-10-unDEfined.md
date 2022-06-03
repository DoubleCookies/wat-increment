---
layout: post
title: unDEfined
author: DoubleCookies
---
This one is more complex:

{% highlight javascript %}
let a = 0;

a = a + (""+a[a])[3].charCodeAt() - (""+a[a])[2].charCodeAt(); // a = 1
{% endhighlight %}

<!--more-->
### Explanation
At first sight this one connected with strings — `charCodeAt()` and `""` are markers for it. 
What exactly happens here?

- `a[a]` return `undefined`. Logically using number as array is crazy but JS can endure it.
- `""+a[a]` return `"undefined"` but as string!
- Finally, we get third and fourth letter from un**de**fined, 
get their codes (`charCodeAt()` will return number) and subtract them!

That's it. This code can be changed a bit because we have more than one possible combination of consecutive letters.