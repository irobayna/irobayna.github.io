---
title: Simple XML to NSDictionary Converter (like in JSON)
author: admin
layout: post
permalink: /2011/01/22/simple-xml-to-nsdictionary-converter-like-in-json/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/ecME9u
categories:
  - iPhone
  - JSON
  - objective-c
  - Xcode
  - XML
---
If you are wondering why, it is because I believe JSON is a much better data exchange protocol than XML.  A few libraries I use for JSON return NSDictionary and NSArray back to you as the result of a parse.  In JSON there is no need to write complex parsers (that you will probably just use one time)

I have found this [very useful resource][1]

it takes something like this as its input:

<pre class="brush:xml">testXMLString = 
    &lt;items&gt;
        &lt;item id=”0001″ type=”donut”&gt;
            &lt;name&gt;Cake&lt;/name&gt;
            &lt;ppu&gt;0.55&lt;/ppu&gt;
            &lt;batters&gt;
                &lt;batter id=”1001″&gt;Regular&lt;/batter&gt;
                &lt;batter id=”1002″&gt;Chocolate&lt;/batter&gt;
                &lt;batter id=”1003″&gt;Blueberry&lt;/batter&gt;
            &lt;/batters&gt;
            &lt;topping id=”5001″&gt;None&lt;/topping&gt;
            &lt;topping id=”5002″&gt;Glazed&lt;/topping&gt;
            &lt;topping id=”5005″&gt;Sugar&lt;/topping&gt;
        &lt;/item&gt;
    &lt;/items&gt;</pre>

and returns the following:

<pre class="brush:shell">xmlDictionary = {
    items = {
        item = {
            id = 0001;
            type = donut;
            name = {
                text = Cake;
            };
            ppu = {
                text = 0.55;
            };
            batters = {
                batter = (
                    {
                        id = 1001;
                        text = Regular;
                    },
                    {
                        id = 1002;
                        text = Chocolate;
                    },
                    {
                        id = 1003;
                        text = Blueberry;
                    }
                );
            };
            topping = (
                {
                    id = 5001;
                    text = None;
                },
                {
                    id = 5002;
                    text = Glazed;
                },
                {
                    id = 5005;
                    text = Sugar;
                }
            );
        };
     };
 }</pre>

 [1]: http://troybrant.net/blog/2010/09/simple-xml-to-nsdictionary-converter/