---
layout: post
title: Adding line numbers to the code block layout for my Jekyll site
description: Easier way to add the line numbers at the left side of my code block layout using few lines of JavaScript and CSS.
keywords: line numbers, code block layout, jekyll site template, line numbers using javascript, line numbers css
tags: [Jekyll, CSS, JavaScript]
comments: true
---

Previously, my code block for this site is just a simply boring code block. Then, I thought I want to make it a little bit fancy by adding the line numbers into it. Finally, I realized it by using few lines of JavaScript code and a little bit of styles using CSS code. Let's the code on how I implemented it for this site (a Jekyll powered site) without using any code syntax-highlighting plugin.

Since the markdown will output the code block into something like `<pre><code>...</code></pre>`, so I can use the JavaScript vanilla to create the line numbers and inject the HTML code into my `<pre><code>` block.

```js
(function() {
  var pre = document.getElementsByTagName('pre'),
      pl = pre.length;
  for (var i = 0; i < pl; i++) {
    pre[i].innerHTML = '<span class="line-number"></span>' + pre[i].innerHTML + '<span class="cl"></span>';
    var num = pre[i].innerHTML.split(/\n/).length;
    for (var j = 0; j < (num - 1); j++) {
      var line_num = pre[i].getElementsByTagName('span')[0];
      line_num.innerHTML += '<span>' + (j + 1) + '</span>';
    }
  }
})();
```

If you want to implement into your site, you can use the JavaScript code above and include it before the `</body>` tag of your Jekyll layout.

Below is my SCSS code for styling the code block layout as you can see on this page right now:

```css
pre {
  display: block;
  margin-top: 0;
  margin-bottom: 1rem;
  font-size: 0.7rem;
  line-height: 1.4;
  white-space: pre;
  overflow: auto;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  padding: .5rem;
  max-height: 800px;
  font-family: monospace;

  code {
    color: inherit;
    background-color: transparent;
    padding: 0;
    display: block;
  }

  .line-number {
    display: block;
    float: left;
    margin: 0 1em 0 -1em;
    border-right: 1px solid #ddd;
    text-align: right;

    span {
      display: block;
      padding: 0 .5em 0 1em;
      color: #ccc;
    }
  }

  .cl {
    display: block;
    clear: both;
  }
}
```

If you want to try and play around with the demo, you can check my [CodePen here](https://codepen.io/heiswayi/pen/jyKYyg), but please note that the markdown in the CodePen does not have automatic code syntax-highlighting like GitHub Pages did for this Jekyll site. Have fun coding!
