---
title: cell.image deprecated
author: admin
layout: post
permalink: /2010/12/31/cell-image-deprecated/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/dUhMru
categories:
  - iPhone
  - objective-c
  - science
  - technology
  - Xcode
---
If you compile your source with >= 3.x versions, we will get a deprecated warning

<pre class="brush:cpp">cell.image = [UIImage imageNamed:@"your_image.png"];</pre>

**should be changed to:**

<pre class="brush:cpp">[cell.imageView setImage:[UIImage imageNamed:@"your_image.png"]];</pre>