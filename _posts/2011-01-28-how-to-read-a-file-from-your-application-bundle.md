---
title: How To Read a File From Your Application Bundle
author: admin
layout: post
permalink: /2011/01/28/how-to-read-a-file-from-your-application-bundle/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/eILhFD
categories:
  - iPhone
  - JSON
  - objective-c
  - Tutorial
---
<pre class="brush:cpp">fileName = @"mydata.json";

	NSString *path = [[[NSBundle mainBundle] resourcePath] stringByAppendingPathComponent:fileName];

	NSData *data = [NSData dataWithContentsOfFile:path];
	if (data) {

		NSString *jsonStr = [[NSString alloc] initWithData:data encoding:NSASCIIStringEncoding];
		NSLog(@"REPLY: %@", jsonStr);

	}</pre>