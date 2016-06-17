---
layout: post
title: Elasticsearch usage Base
date: 2016-06-15 15:27:31
---

原来使用elasticsearch只是用他的简单配方，分词也是网上抄的。

1. model分词配置

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

