---
layout: post
title: Add Custom Classes to Wordpress Posts
categories: Wordpress
excerpt: While developing my latest WordPress plugin, <a href="https://wordpress.org/plugins/initial-letter/" target="_blank">Initial Letter</a>, I needed to figure out how to add a custom class to the post container.
---

<p>While developing my latest WordPress plugin, <a href="https://wordpress.org/plugins/initial-letter/" target="_blank">Initial Letter</a>, I needed to figure out how to add a custom class to the post container.  While I actually didn't end using this method I figured it would be an easy thing to share in case others were looking to do the same thing.</p>
<p>Basically it comes down to adding a filter which ties into the &#8216;post_class&#8217; hook.  Keep in mind that this will only work if the theme you're using implements the <a href="http://codex.wordpress.org/Function_Reference/post_class" target="_blank">post_class()</a> function, which pretty much all themes should use.</p>

{% highlight ruby %}
// Add 'initial_letter_post' class to post container
function initial_letter_plugin_class_filter($classes) {
	$classes[] = 'initial_letter_post';
	return $classes;
}

add_filter( 'post_class', 'initial_letter_plugin_class_filter');
{% endhighlight %}
