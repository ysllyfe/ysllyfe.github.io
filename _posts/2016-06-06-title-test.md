---
layout: post
title: Rails Elasticsearch
date: 2016-06-15 19:13:31
---

rails 项目引用了 elasticsearch 做为全文检索

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

