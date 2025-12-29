---
title: Ruby 4.0... What's New
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/gems.jpeg"
description: High level recap of Ruby 4.0 features
tags:
- Ruby
- Programming
- Versions
---

Here is an overview of Ruby 4.0 and its features.  

Ruby 4.0 was released in December 25, 2025 with new features that improve the language's capabilities and make it even more useful for developers. In this blog post, we'll explore some of the most exciting features in Ruby 4.0.  

**ZJIT**  
A new prototype JIT compiler pitched as the 'next generation' of YJIT. It aims to offer extra performance in the long term but isn't considered production ready yet, so it's behind a --zjit flag if you want to test it out.

**Ruby Box**  
Ruby Box is an experimental isolation feature for separating definitions (monkey patches, globals, class definitions). It's akin to what you might call namespaces elsewhere (and stems largely from a proposal to include namespaces into Ruby) but differs enough to warrant the term 'box'. 

**Net::HTTP**  
Net::HTTP no longer auto-sets Content-Type. You must now explicitly set it for POST/PUT requests. This is quite a significant, yet subtle, breaking change with potentially negative outcomes, particularly when using API clients that aren't updated for Ruby 4.0.

**Kernel#inspect**  
Kernel#inspect's output can now be customized with which instance variables you want to display – potentially useful for hiding sensitive data like tokens.

**Language changes**  
- Logical operators can now start lines and will continue the expression from the previous line (akin to method chaining with .). 

- Backtraces are cleaner, with internal frames hidden meaning C-implemented methods now show the Ruby source location. 

- Ractors have seen some improvements, but remain experimental for now (though the aim is for the experimental status to be removed later in 2026). 

- Set is now a core class and no longer needs to be autoloaded on use. 

- Array#rfind is a new, more efficient alternative to arr.reverse_each.find. 

- A myriad of performance boosts, like a faster Class#new and faster GC. 

- Ruby 4.0 is now available in the official Ruby Docker images.  
  

You can read more details about Ruby 4.0 by [clicking here](https://www.ruby-lang.org/en/news/2025/12/25/ruby-4-0-0-released/).