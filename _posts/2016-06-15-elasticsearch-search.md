---
layout: post
title: Elasticshearch search
date: 2016-05-07 15:27:31
---

test

中文

I am a placeholder post. Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

> Boom. I am a blockquote.1
>
> Say something really clever here.

1. List with code

```
  settings analysis: {
    analyzer: {
      charSplit: {
        type: 'custom',
        tokenizer: 'ngram_tokenizer'
      }
    },
    tokenizer: {
      ngram_tokenizer: {
        type: 'nGram',
        min_gram: 1,
        max_gram: 1,
        token_chars: ['letter','digit','punctuation']
      }
    }
  }
  settings index:{ number_of_shards: 1, number_of_replicas: 0 } do
    mapping do
      indexes :plate_no,      analyzer: 'charSplit'
    end
  end
```
2. List with code{% highlight javascript %}
var dom = document.getElementById('boom')
console.log(dom);{% endhighlight %}

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

{% highlight ruby %}
def whaaa
  puts "I have a friend called Bobobmob."
end
{% endhighlight %}

