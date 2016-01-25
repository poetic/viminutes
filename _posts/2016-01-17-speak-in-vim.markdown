---
layout: post
title:  "Speak in vim"
date:   2016-01-17 10:30:01
---
## Problems
- delete a chunk of code

{% highlight javascript %}
// FROM
var user = {
  fullName() {
    return this.firstName + ' ' + this.lastName;
  }
}
// TO
var user = {
}
{% endhighlight %}

- change a chunk of code
{% highlight javascript %}
// FROM
var user = {
  fullName() {
    return this.firstName + ' ' + this.lastName;
  }
}
// TO
var user = {
  fullName() {
    throw new Error('not implemented');
  }
}
{% endhighlight %}

- copy a whole file

## Concepts
- basic vim **syntax**:
  - `<command><text modifier><text object>`
  - `<command><motion>` (NOTE: incomming!)
- commands
  - c (change)
  - d (delete)
  - y (yank)
  - gc (toggle comment) [vim-commentary](https://github.com/tpope/vim-commentary)
- text modifiers
  - a (around)
  - i (inside)
  - s (surround) [vim-surround](https://github.com/tpope/vim-surround)
- text objects
  - w (word)
  - p (paragraph)
  - e (entire file) [vim-textobj-entire](https://github.com/kana/vim-textobj-entire)
  - {
  - \[
  - t (html tag)
  - c (chunk) [vim-textobj-javascript](https://github.com/poetic/vim-textobj-javascript)

## Exercises
- delete a chunk of code
{% highlight javascript %}
// FROM
var name = 'wrong';
// TO
var name = 'right';
{% endhighlight %}

- duplicate a paragraph
{% highlight javascript %}
// FROM

var name = function() {
  return name;
}

// TO

var name = function() {
  return name;
}

var name = function() {
  return name;
}

{% endhighlight %}

- delete code inside quote
{% highlight javascript %}
// FROM
var name = 'this is too long';
// TO
var name = '';
{% endhighlight %}

## Q&A

## Resources
- [vim text objects](http://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/)
- [a list of custom text objects](https://github.com/kana/vim-textobj-user/wiki)
