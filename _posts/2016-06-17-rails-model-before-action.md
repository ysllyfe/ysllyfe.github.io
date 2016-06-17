---
layout: post
title: Rails model before_save
date: 2016-06-17 19:18:24
---

在做model层根据相关性赋值的时候，喜欢放在before_save中，结果又给忘了return。

在最后一行如果是条件语句的情况下，如果为false会阻止代码的继续执行

具体的activerecord callbacks
[http://api.rubyonrails.org/classes/ActiveRecord/Callbacks.html]()
