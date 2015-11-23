---
title: 'Flatten&#8221; HTML Content (i.e strip tags) in Cocoa/Objective-C'
author: admin
layout: post
permalink: /2010/12/09/flatten-html-content-i-e-strip-tags-in-cocoaobjective-c/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/fIeOf0
categories:
  - iPhone
  - objective-c
  - technology
---
Interesting post about removing html tags in a NSString: <span style="font-size: 11.6667px;"><a href="http://bit.ly/dWpEOV">http://bit.ly/dWpEOV</a></span>

<span style="font-size: 11.6667px;">Basic idea is to use the NSScanner class</span>

<span style="font-size: 11.6667px;"> </span>

<pre class="brush:cpp">nsscanner *thescanner;
    nsstring *text = nil;

    thescanner = [nsscanner scannerwithstring:html];

    while ([thescanner isatend] == no) {

        // find start of tag
        [thescanner scanuptostring:@"&lt;" intostring:null] ; 

        // find end of tag
        [thescanner scanuptostring:@"&gt;" intostring:&text] ;

        // replace the found tag with a space
        //(you can filter multi-spaces out later if you wish)
        html = [html stringbyreplacingoccurrencesofstring:
                           [ nsstring stringwithformat:@"%@&gt;", text]
                     withstring:@" "];

    } // while //</pre>