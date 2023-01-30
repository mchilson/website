---
title: Ruby 3.0 - Promises Delivered
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/gems.jpeg"
description: Overview of Ruby 3.0 and its features.
tags:
- Ruby
- Programming
- Review
---

After five years of hard work by the core language team, Ruby 3.0 was released on Christmas 2020 with better performance and other features for this high-level general-purpose programming language.

Why am I writing a review six months later? I wanted to get plenty of "hands-on" time with the new version before commenting on it. Let's get going...

Ruby 3.0 was developed with a focus on better performance, concurrency, and typing and achieved its goal of being 3x faster than the performance of Ruby 2.0. That 3x speed-up is when making use of the new Ruby 3.0 Just-In-Time (JIT) compiler. Even without the JIT feature, its VM implementation is still substantially faster compared to Ruby 2.

Ruby 3.0's JIT seems to show its speed mostly where there are a few methods being called many times. Ruby 3.1 is expected to improve the JIT performance more for workloads with a greater number of methods.

Ruby 3.0 also ships the experimental "Ractor" for a parallel execution feature without thread-safety concerns, the Fiber Scheduler allows intercepting blocking operations, static analysis improvements, improved one-line pattern matching, and many other changes.

Overall, this release is a substantial step forward and when combined with the upcoming Rails 7 release should eliminate any performance issues as long as good coding practices are followed.

For more details on the Ruby 3.0 release [click here](https://www.ruby-lang.org/en/news/2020/12/25/ruby-3-0-0-released/).