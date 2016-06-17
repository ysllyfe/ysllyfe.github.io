---
layout: post
title: Elasticsearch usage Base
date: 2016-06-15 15:27:31
---

原来使用elasticsearch只是用他的简单配方，分词也是网上抄的。
出现问题的情况是在检索车牌号码的时候，如粤A123456时，如果只是不带中文的情况下，检索不到数据，分词的问题。解决问题如下

model分词配置

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
      indexes :model_column,      analyzer: 'charSplit'
    end
  end
```

