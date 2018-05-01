---
layout: page
title: Projects
description: Hyperlinks to some of my projects and snippets.
keywords: projects page, hyperlinks, my snippets
---

## Published Posts tagged with "Project"...

<ul>
  {% for post in site.posts %}
    {% if post.tags contains "Project" %}

    <li>
        <a href="{{ post.url }}"><strong>{{ post.title }}</strong></a> - {{ post.description }}
    </li>

    {% endif %}
  {% endfor %}
</ul>

## More Projects...

### Using GitHub API and hosted using GitHub Pages

- [**heiswayi.github.gists**](https://heiswayi.github.io/my-gists/) - A personalized listing site I built to show all of my public GitHub Gists including some code snippets.
- [**heiswayi nrird github repositories**](https://heiswayi.github.io/my-repos/) - A personalized listing site I built to show all of my public GitHub repositories including some of my Open Source projects.

### Hosted using GitHub Pages

- [**PGP Key Generator**](https://heiswayi.github.io/pgp/) - Safer and easy-to-use client-side PGP keys generator.
- [**Spelling: UK vs US**](https://heiswayi.github.io/spelling-uk-vs-us) - A comprehensive* list of British vs. American spelling differences.
- [**Math Console**](https://heiswayi.github.io/math-console/) - A basic Mathematical-powered console to evaluate basic arithmetic operations, common math functions and also to convert a math unit to another. Some constants are supported too.
- [**Color Contrast Checker**](https://heiswayi.github.io/color-contrast-checker) - A simple color tool to evaluate and check your color contrast ratios between foreground and background colors.
- [**EncryptJS**](https://heiswayi.github.io/encryptjs/) - A JavaScript library for encrypting message and embed it as HTML code into your web content.
- [**W4Y1**](https://heiswayi.github.io/w4y1/) - My personal experimental AI chatbot for self reflection.
- [**Random Name Picker**](https://heiswayi.github.io/random-name-picker/) - Simple HTML tool to randomly pick a name from a list I once made to use for indoor events.
- [**Markdown-HTML Live Preview Editor**](https://heiswayi.github.io/markdown-editor) - A very simple markdown-to-HTML live preview editor made in JavaScript vanilla.

### Scripts hosted by nrird.xyz

- [**Web Proxy Script**](https://nrird.xyz/proxy/) - My personal web proxy script.
- [**Whois Script**](https://nrird.xyz/scripts/whois/) - Simple domain whois script that supports up to 1195 domain name extensions.
- [**Indenter Tool**](https://nrird.xyz/scripts/indenter-tool/) - Simple script to prettify and fix indentation of the code.
- [**JS Packer**](https://nrird.xyz/scripts/js-packer/) - Simple script to compress and obfuscate JavaScript code.
- [__More scripts...__](https://nrird.xyz/scripts/)

### Generators hosted by nrird.xyz

- [**FREE Ultimate Blocks**](https://nrird.xyz/ultimate-blocks) - A FREE block-based HTML drag-and-drop bootstrap theme builder with 126+ predesigned unique blocks and unlimited variants.
- [**Personal URL Shortening Service**](https://nrird.xyz/scripts/url-shortener/) - My personal URL shortener script.
- [**Static Sparkline Image Generator**](https://nrird.xyz/scripts/sparkline/) - PHP script to generate static sparkline image with browser caching with ETag.

### Miscellaneous stuffs hosted by nrird.xyz

- [**Website Checklist**](https://nrird.xyz/website-checklist) -  Checklist for starting a website.
- [**Encrypto Zero**](https://nrird.xyz/encrypto-zero) - Just another minimalist, secure and encrypted pastebin app for personal use purpose.
- [**Document Writer**](https://nrird.xyz/document-writer) - A minimalist web-based writing tool to write document using web browser.
