---
layout: post
title: "Markdown syntax"
categories: [Programming]
tags: [markdown]
comments: true
---

<a name="headers"></a>

### HEADERS
```
# This is an h1 tag
## This is an h2 tag
###### This is an h6 tag
```

<!--more-->

# This is an h1 tag
## This is an h2 tag
###### This is an h6 tag

<a name="lists"></a>

### LISTS

<a name="unordered"></a>

### Unordered
```
* Item 1
* Item 2
  * Item 2a
  * Item 2b
```
* Item 1
* Item 2
  * Item 2a
  * Item 2b

<a name="ordered"></a>

### Ordered
```
1. Item 1
2. Item 2
3. Item 3
   * Item 3a
   * Item 3b
```
1. Item 1
2. Item 2
3. Item 3
   * Item 3a
   * Item 3b

<a name="images"></a>

### IMAGES
```
![Screenshot home page](/images/screenshot-homepage.png)
Format: ![Alt Text](url)
```

![Screenshot home page](https://raw.githubusercontent.com/qndev/blog/gh-pages/images/posts/screenshot.png)

<a name="emphasis"></a>

### EMPHASIS
```
*This text will be italic*
_This will also be italic_

**This text will be bold**
__This will also be bold__

_You **can** combine them_

```
*This text will be italic*
_This will also be italic_

**This text will be bold**
__This will also be bold__

_You **can** combine them_

<a name="links"></a>

### LINKS
```
http://github.com - automatic!
[GitHub](http://github.com)
```
http://github.com - automatic!
[GitHub](http://github.com)

<a name="blockquotes"></a>

### Blockquotes
```
As Grace Hopper said:

> I’ve always been more interested
> in the future than in the past.
```
As Grace Hopper said:

> I’ve always been more interested
> in the future than in the past.

<a name="highlighting"></a>

### Syntax highlighting
```javascript
function test() {
console.log("look ma’, no spaces");
}
```

<a name="task-lists"></a>

### Task Lists
```
- [x] this is a complete item
- [ ] this is an incomplete item
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
```
- [x] this is a complete item
- [ ] this is an incomplete item
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)

<a name="emoiji"></a>

### EMOJI
```
GitHub supports emoji!
:+1: :sparkles: :camel: :tada:
:rocket: :metal: :octocat:
```
GitHub supports emoji!
:+1::sparkles::camel::tada::rocket::metal::octocat:

---
