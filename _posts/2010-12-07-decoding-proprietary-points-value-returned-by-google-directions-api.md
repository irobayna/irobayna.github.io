---
title: 'Decoding proprietary &#8216;points&#8217; value returned by Google directions API'
author: admin
layout: post
permalink: /2010/12/07/decoding-proprietary-points-value-returned-by-google-directions-api/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/i9XP22
categories:
  - iPhone
  - objective-c
---
<pre class="brush:cpp">NSInteger len = [encoded length];
	NSInteger index = 0;
	NSMutableArray *array = [[[NSMutableArray alloc] init] autorelease];
	NSInteger lat=0;
	NSInteger lng=0;
	while (index &lt; len) {
		NSInteger b;
		NSInteger shift = 0;
		NSInteger result = 0;
		do {
			b = [encoded characterAtIndex:index++] - 63;
			result |= (b & 0x1f) &lt;&lt; shift;
			shift += 5;
		} while (b &gt;= 0x20);
		NSInteger dlat = ((result & 1) ? ~(result &gt;&gt; 1) : (result &gt;&gt; 1));
		lat += dlat;
		shift = 0;
		result = 0;
		do {
			b = [encoded characterAtIndex:index++] - 63;
			result |= (b & 0x1f) &lt;&lt; shift;
			shift += 5;
		} while (b &gt;= 0x20);
		NSInteger dlng = ((result & 1) ? ~(result &gt;&gt; 1) : (result &gt;&gt; 1));
		lng += dlng;
		NSNumber *latitude = [[[NSNumber alloc] initWithFloat:lat * 1e-5] autorelease];
		NSNumber *longitude = [[[NSNumber alloc] initWithFloat:lng * 1e-5] autorelease];

		CLLocation *loc = [[[CLLocation alloc] initWithLatitude:[latitude floatValue] longitude:[longitude floatValue]] autorelease];

		[array addObject:loc];
	}</pre>