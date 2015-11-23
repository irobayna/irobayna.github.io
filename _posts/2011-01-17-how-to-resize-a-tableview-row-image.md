---
title: How to resize a tableView row image?
author: admin
layout: post
permalink: /2011/01/17/how-to-resize-a-tableview-row-image/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/f1YC2Y
categories:
  - iPhone
  - objective-c
  - technology
  - Tutorial
---
<pre class="brush:cpp">UIImage *cellImage = [UIImage imageNamed:@"Image.png"]; 
[cell.imageView setImage:tableImage]; 
CGSize imageSize = CGSizeMake(45,55);	
UIGraphicsBeginImageContext(imageSize); 
CGRect imageRect = CGRectMake(1.0, 1.0, imageSize.width, imageSize.height); 
[cellImage drawInRect:imageRect]; 
cell.imageView.image = UIGraphicsGetImageFromCurrentImageContext(); 
UIGraphicsEndImageContext();</pre>