---
layout: post
title: Select All Text Box Wordpress Plugin
categories: Wordpress
excerpt: Here's another simple WordPress plugin I came up with.  I was trying to figure out an easy way to create a text box for some song lyrics which, once clicked, selected everything inside so anyone could easily copy and past the contents.  Well, once I figured out how to make it I figured I would make it easier for others who want to do the same thing.  Hence, Simple Select All Text box was born.
---

Here's another simple WordPress plugin I came up with.  I was trying to figure out an easy way to create a text box for some song lyrics which, once clicked, selected everything inside so anyone could easily copy and past the contents.  Well, once I figured out how to make it I figured I would make it easier for others who want to do the same thing.  Hence, Simple Select All Text box was born.

<p><a class="button" title="Download Simple Select All Text Box Plugin" href="http://wordpress.org/extend/plugins/simple-select-all-text-box/" target="_blank">Download Plugin</a></p>
<h2>Instructions:</h2>
<p>To create a text box in a post or a page use this shortcode:</p>
<p><pre>[textbox rows="3"]Contents of text box[/textbox]</pre></p>
<p>Options are as follows:</p>
<ul>
	<li><code>rows</code> Number of text rows.  This will determine the height of the text box. (optional)</li>
	<li><code>width</code> Width of the text box in pixels. (optional)</li>
	<li><code>code</code> When set to <b>true</b> the content of the text box will not be escaped. Useful for including code snippets. (optional)</li>
	<li><code>class</code> Specifies a custom class to use on the text box.  Useful for styling. (optional)</li>
</ul>
<h2>Installation:</h2>
<ol>
	<li>Upload the whole simple-select-all-textbox folder to the /wp-content/plugins/ directory.</li>
	<li>Activate the plugin through the Plugins menu in WordPress.</li>
	<li>Go to the options page to adjust the width of all text boxes made using this shortcode.</li>
</ol>
<h2>Example:</h2>
<textarea rows="3" class="form-control" onClick="this.focus();this.select();" onChange="this.value = this.getAttribute('data-content');" data-content="And we could pretend it all the time
Can't you see that it's just raining?
There ain't no need to go outside">And we could pretend it all the time
Can't you see that it's just raining?
There ain't no need to go outside</textarea>