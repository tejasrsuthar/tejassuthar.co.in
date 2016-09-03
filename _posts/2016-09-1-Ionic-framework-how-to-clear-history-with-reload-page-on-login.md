---
layout: post
title: Ionic Framework - How to clear history with reload page on login logout
description: "Ionic article about How to clear history with reload page on login logout"
modified: 2016-09-01
tags: [Ionic Framework, ui-router]
image:
  feature: desk.jpg
---


While working with my Hybrid Mobile Application with Ionic framework, often I need to clear navigation history and redirect users to Login page. Also needs to make sure, On login and logout I need to reload the page, in order to refresh the data, however, $state.go('homePage') takes the user back to the view without reloading - the controller behind it is not called.

The routing in Ionic is powered by [ui-router](https://github.com/angular-ui/ui-router) AngularJS module. 

### Solution: 
There are couple of ways to solve this problem. 

This will just reload the state
{% highlight php linenos %}
$state.go($state.current, {}, {reload: true});
{% endhighlight %}
 
This will actually reload the page
{% highlight php linenos %}
$window.location.reload(true)
{% endhighlight %}

Using any of those solution will fix your problem. 