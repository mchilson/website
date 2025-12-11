---
title: Ruby 3.4... What's New
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/gems.jpeg"
description: High level recap of Ruby 3.4.7 features
tags:
- Ruby
- Programming
- Versions
---

I am late getting this post out about Ruby 3.4 in general but here is an overview of 3.4 and its features.

Ruby 3.4 was released in December 2024 with new features that improve the language's capabilities and make it even more useful for developers. In this blog post, we'll explore some of the most exciting features in Ruby 3.4.

**it is introduced**
it is added to reference a block parameter with no variable name. 

'''
ary = ["foo", "bar", "baz"]
p ary.map { it.upcase } #=> ["FOO", "BAR", "BAZ"]
'''

it very much behaves the same as _1. When the intention is to only use _1 in a block, the potential for other numbered parameters such as _2 to also appear imposes an extra cognitive load onto readers. So it was introduced as a handy alias. Use it in simple cases where it speaks for itself, such as in one-line blocks.

**Prism is now the default parser**
Switched the default parser from parse.y to Prism. 
This is an internal improvement and there should be little change visible to the user. If you notice any compatibility issues, please report them to us. 
To use the conventional parser, use the command-line argument --parser=parse.y. 

**The socket library now features Happy Eyeballs Version 2**
The socket library now features Happy Eyeballs Version 2 (RFC 8305), the latest standardized version of a widely adopted approach for better connectivity in many programming languages, in TCPSocket.new (TCPSocket.open) and Socket.tcp. This improvement enables Ruby to provide efficient and reliable network connections, adapted to modern internet environments.

Until Ruby 3.3, these methods performed name resolution and connection attempts serially. With this algorithm, they now operate as follows:

Performs IPv6 and IPv4 name resolution concurrently
Attempt connections to the resolved IP addresses, prioritizing IPv6, with parallel attempts staggered at 250ms intervals
Return the first successful connection while canceling any others
This ensures minimized connection delays, even if a specific protocol or IP address is delayed or unavailable. This feature is enabled by default, so additional configuration is not required to use it. To disable it globally, set the environment variable RUBY_TCP_NO_FAST_FALLBACK=1 or call Socket.tcp_fast_fallback=false. Or to disable it on a per-method basis, use the keyword argument fast_fallback: false.

**YJIT**
Better performance across most benchmarks on both x86-64 and arm64 platforms.
Reduced memory usage through compressed metadata and a unified memory limit.
Various bug fixes: YJIT is now more robust and thoroughly tested.

**Language changes**
String literals in files without a frozen_string_literal comment now emit a deprecation warning when they are mutated. These warnings can be enabled with -W:deprecated. To disable this change, you can run Ruby with the --disable-frozen-string-literal command line argument. 

Keyword splatting nil when calling methods is now supported. **nil is treated similarly to **{}, passing no keywords, and not calling any conversion methods. 

Block passing is no longer allowed in index. 

Keyword arguments are no longer allowed in index. 

The toplevel name ::Ruby is reserved now, and the definition will be warned. 

You can read more details about Ruby 3.4 by [clicking here](https://www.ruby-lang.org/en/news/2024/12/25/ruby-3-4-0-released/).