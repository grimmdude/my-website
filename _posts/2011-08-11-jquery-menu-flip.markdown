---
layout: post
title: menuFlip - jQuery Plugin for Flipping Navigation
categories: Wordpress
excerpt: Here's another simple WordPress plugin I came up with.  I was trying to figure out an easy way to create a text box for some song lyrics which, once clicked, selected everything inside so anyone could easily copy and past the contents.  Well, once I figured out how to make it I figured I would make it easier for others who want to do the same thing.  Hence, Simple Select All Text box was born.
---

<style type="text/css" media="screen">
	ul#flip_nav {
		background-color:#ffffff;
		border:none;
		overflow:hidden;
	}

	ul#flip_nav li {
		list-style:none;
		float:left;
		text-align:center;
		margin:0px 10px 0px 0px;

		/*bare bones required css (feel free to change the height though)*/
		height:20px;
		overflow:hidden;
	}

	ul#flip_nav li a  {
		font-family:helvetica;
		font-size:12px;
		color:#3f3f3f;
		text-transform:uppercase;
		text-decoration:none;
		background-color:white;
		margin:0px;
		padding:0px 5px 0px 5px;

		/*bare bones required css*/
		display:block;
	}

	/*this defines the styling of the new flipped menu item*/
	ul#flip_nav li a.flipped_item {
		background-color:#000000;
		color: #ffffff;
	}
</style>
<p>menuFlip is a jQuery plugin for adding a flipping, marquee type effect to text based navigational menu items when hovered over without needing to use background images, which can be a pain.</p>
<p><a href="https://github.com/grimmdude/jQuery-menuFlip/archive/master.zip" class="button">Download</a></p>
<p><a href="https://github.com/grimmdude/jQuery-menuFlip" title="jQuery menuFlip Plugin" target="_blank">View source on GitHub</a></p>
<h2>Menu Example</h2>
<ul id="flip_nav">
	<li><a href="javascript:;">Home</a></li>
	<li><a href="javascript:;">Web</a></li>
	<li><a href="javascript:;">Blog</a></li>
	<li><a href="javascript:;">Contact</a></li>
</ul>
<h2>HTML</h2>
<p>All you need is this simple markup.</p>
{% highlight html %}
<ul id="flip_nav">
	<li><a href="/home">Home</a></li>
	<li><a href="/web">Web</a></li>
	<li><a href="/blog">Blog</a></li>
	<li><a href="/contact">Contact</a></li>
</ul>
{% endhighlight %}
<p>You can optionally specify the text you want to use for the flipped menu item using the <code>data-flipped-text</code> attribute in each link:</p>
{% highlight html %}
<li><a href="/home" data-flipped-text="Flipped Text">Home</a></li>
{% endhighlight %}
<h2>Calling the Plugin</h2>
{% highlight javascript %}
$('#flip_nav).menuFlip({
    li_height       : '20px', 
    flip_speed      : 150, 
    flipped_class   : 'flipped_item', 
    mouseover       : function() {}, 
    mouseout        : function() {}
});
{% endhighlight %}
<h2>CSS</h2>
<p>No extra CSS is required for this plugin to function, but you'll probably want to define a width for the <code>ul</code> or float the <code>li</code> elements to the left so they are inline.  Also, the flipped items have a class of <code>flipped_item</code> so you can style that puppy as you like.  Here's an example of the CSS for the above example:</p>
{% highlight css %}
ul#flip_nav li {
	float:left;
	text-align:center;
	margin:0px 10px 0px 0px;
}

/*this defines the styling of the new flipped menu item*/
ul#flip_nav a.flipped_item {
	background-color:#000000;
	color: #ffffff;
}
{% endhighlight %}
<script   src="https://code.jquery.com/jquery-1.12.4.min.js" integrity="sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=" crossorigin="anonymous"></script>
<script type='text/javascript' src='/assets/js/jquery.menuflip.js'></script>
<script>jQuery('#flip_nav').menuFlip();</script>