---
title: Calculate distance between two locations
author: admin
layout: post
permalink: /2010/12/13/calculate-distance-between-two-locations/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/i6zaQS
categories:
  - iPhone
  - objective-c
  - Tutorial
---
If you have two CLLocations and are wondering how to calculate the distance in between, here is how:

<pre class="brush:cpp" style="padding-left: 30px;">CLLocation *location1 = [[CLLocation alloc] initWithLatitude:42.333297
                        longitude:-71.588858];

CLLocation *location2 = [[CLLocation alloc] initWithLatitude:42.353297
                       longitude:-71.578858];

float distanceInBetween = [location1 getDistanceFrom:location2];</pre>

The code above is ***deprecated***, the new code should look like:

<pre class="brush:cpp">CLLocationDistance kilometers;
kilometers = [location1 distanceFromLocation:location2] / 1000;</pre>