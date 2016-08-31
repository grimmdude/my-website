---
layout: post
title: Delete Duplicate WordPress Comments
categories: Wordpress
excerpt: I ran into a situation recently where all of the comments on a blog I was working on got doubled up, so I had to figure out a way to get rid of the extra ones.  I read some solutions involving using two MySQL tables but I was hoping to avoid dealing with all that.
---

I ran into a situation recently where all of the comments on a blog I was working on got doubled up, so I had to figure out a way to get rid of the extra ones.  I read some solutions involving using two MySQL tables but I was hoping to avoid dealing with all that.

I ended up writing this script that basically goes through each comment and checks if another comment with the same content exists on the same post, and if so deletes it.  It's pretty simple I think and worked like a charm for me so I thought I'd share it here.  Remember to always backup your database before running any kind of fixes like this, just in case.

<script src="https://gist.github.com/grimmdude/5828710.js"></script>