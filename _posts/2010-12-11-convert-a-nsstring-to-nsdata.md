---
title: Convert a NSString to NSData and NSData to NSString
author: admin
layout: post
permalink: /2010/12/11/convert-a-nsstring-to-nsdata/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/fw1wBv
categories:
  - iPhone
  - objective-c
  - Tutorial
  - Xcode
---
**Convert NSData to NSString:**

<pre class="brush:cpp">NSString *str= @"this is a string";
NSData *data=[str dataUsingEncoding:NSUTF8StringEncoding];
</pre>

**Convert NSData to NSString (ASCII encoding assumed)**:

<pre class="brush:cpp">NSString *str = [NSString stringWithCString:[data bytes] length:[data length]];
</pre>