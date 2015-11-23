---
title: How to include some code only during DEBUG builds
author: admin
layout: post
permalink: /2010/12/11/how-to-include-some-code-only-during-debug-builds/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/hOiARI
categories:
  - iPhone
  - objective-c
  - Tutorial
  - Xcode
---
You need to set a compiler flag.  Go to target then either get Info or double click your target, make sure you have selected the Debug configuration  and look for Other C Flags. (GCC4.2 Language section)

Then add the following as a value: **-DDEBUG**

Now you can simply do

<pre><span style="font-family: monospace;">


<pre class="brush:cpp"> #ifdef DEBUG
NSLog(@"Debug mode running");
#endif</pre>


<p>
  </span>
</p>