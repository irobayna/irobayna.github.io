---
title: '&#8216;-&#8216; vs &#8216;+&#8217; in objective-c methods'
author: admin
layout: post
permalink: /2011/01/27/vs-in-objective-c-methods/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/hGBUAe
categories:
  - iPhone
  - objective-c
  - Tutorial
---
## Did you ever wonder what the meaning is between a &#8216;-&#8216; or a &#8216;+&#8217; to the left of a method ?

for instance:

<pre class="brush:cpp">- (void)loadInfoFile;</pre>

versus

<pre class="brush:cpp">+ (void)loadInfoFile;</pre>

The first is a regular method and the second is a **class **method.

<span style="color: #333333;">In plain English, you do not need to instantiate an object of the second one in order to call it</span>