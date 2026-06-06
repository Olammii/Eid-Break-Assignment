# Theory
## Difference between ```<em>``` and ```<i>```. When to use.
**The core difference is the semantic meaning**

```<em>```tag is used to define emphasized text. the ccontent inside is typically displayed italic. screen reader will pronouce the words in ```<em>``` with an emphasis using verbal stress. by default, the browser set font-syle of ```<em>``` to italic

 while ```<i>``` for text to stand out from normal prose but doesn't covery extra importance or vocal emphasis.

 ```html
<p>You <em>must</em> come to school tommorrow.</p>
```
<p>You <em>must</em> come to school tommorrow.</p>

``` html
<p>You <i>must</i> come to school tommorrow.</p>
 ```
 <p>You <i>must</i> come to school tommorrow.</p>

 ## Screen Reader treat certain elements specially

 1. Header tag ```<header>```.
 2. Nav tag ```<nav>```
 3. footer section ```<footer>```

```<header>```

Represent introductory content , a group of introductory content or navigational aids, also 

```<nav>```

Represent section of page which provide navigation links.

```footer```

contain information about the author of section copyright data, or links to related documents.


## ARIA 

* Using ARIA 