---
title: Adding UILabel programatically
author: admin
layout: post
permalink: /2011/01/11/adding-uilabel-programatically/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/g79uH4
categories:
  - objective-c
  - technology
  - Tutorial
  - Xcode
---
<pre class="brush:cpp">UILabel	*legalLabel = [[UILabel alloc] initWithFrame:CGRectMake(10, 10, 300, 120)];
	legalLabel.lineBreakMode = UILineBreakModeWordWrap;
	legalLabel.numberOfLines = 0;

	//legalLabel.textAlignment =  UITextAlignmentCenter;
	legalLabel.textColor = [UIColor whiteColor];
	legalLabel.backgroundColor = [UIColor blackColor];
	legalLabel.font = [UIFont fontWithName:@"Arial Rounded MT Bold" size:(14.0)];

	legalLabel.text = NSLocalizedString(@"legal_disclaimer",@""); 
	[self.view addSubview:legalLabel];</pre>