---
layout: post
title:  "Vim snippets"
date:   2016-02-02 09:07:01
---
## Recap [flow in tmux](http://poetic.github.io/viminutes/2016/01/17/speak-in-vim.html)
gem install tmuxinator

## Problem
How can I create such a block of code with only two strocks?
{% highlight javascript %}
React.createClass({
  displayName: '',

  getDefaultProps: () => {
    return {
    };
  },

  render: () => {
    return (
      <div>
      </div>
    )
  }
})
{% endhighlight %}

## Solution
vim snippets to the rescue!

{% highlight sh %}
cd ~/.vim/bundle/vim-snippets/snippets
vim javascript.snippets
{% endhighlight %}

{% highlight javascript %}
snippet fn
  function ${1:function_name} (${2}) {
    ${0}
  }
{% endhighlight %}

## Exercise
create your snippet!


## Warning!
Your change will be lost after you update your vim.
I would recommand you at least create a git repo for it.
And sync up to github.
