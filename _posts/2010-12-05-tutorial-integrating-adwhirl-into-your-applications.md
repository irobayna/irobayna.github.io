---
title: 'Tutorial: integrating AdWhirl into your applications'
author: admin
layout: post
permalink: /2010/12/05/tutorial-integrating-adwhirl-into-your-applications/
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/fVxl2p
categories:
  - iPhone
  - objective-c
  - technology
  - Tutorial
tags:
  - iphone
  - objective c
  - tutorial
---
Work in progress&#8230;.

1) Inside your ViewController.h:

#import &#8220;AdWhirlView.h&#8221;  
#import &#8220;AdWhirlDelegateProtocol.h&#8221;

2)

@interface ViewController : UIViewController <AdWhirlDelegate>{  
//your code

3) Inside your ViewController.m:

above the @implementation:

#define kSampleAppKey @&#8221;yourAdWhirlKey&#8221;

4) Inside the @implementation:

#pragma mark AdWhirlDelegate methods

&#8211; (NSString *)adWhirlApplicationKey{  
return kSampleAppKey;  
}

&#8211; (UIViewController *)viewControllerForPresentingModalView{  
return self;  
}

Now for section 7:

5) Inside your ViewController.m

&#8211; (void)viewDidLoad {

[super viewDidLoad];

AdWhirlView *awView = [AdWhirlView requestAdWhirlViewWithDelegate:self];

[self.view addSubview:awView];