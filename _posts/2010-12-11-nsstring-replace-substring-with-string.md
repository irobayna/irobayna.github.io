---
title: NSString replace substring with string
author: admin
layout: post
permalink: /2010/12/11/nsstring-replace-substring-with-string/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/dFxk3e
categories:
  - iPhone
  - objective-c
  - Tutorial
---
<pre class="brush:cpp">NSString *str = @"A animal can fly";

str = [str stringByReplacingOccurrencesOfString:@"animal"
                                     withString:@"duck"];</pre>