---
title: "Ruby and the Traveling Salesman Problem (Help me Neural Net!)"
layout: post
post-image: "https://s3.amazonaws.com/mikechilson-blog-assets/delivery-photo-93398.jpeg"
description: Neural Nets in Ruby.
tags:
- Ruby
- Neural Nets
- GEM File
---

On a recent project we had the task of solving a physical routing problem in a large warehouse, also know as The Traveling Salesman Problem (TSP). The TSP in a nutshell is this: Given a list of physical locations (cities,addresses, etc) and the distances between each pair of them, what is the shortest possible route that visits each location exactly once and returns to the starting location?

Sounds simple for our complex brains to plot this out, but not so simple for a computer program. Enter Artificial Intelligence, specifically Genetics Algorithms in Ruby using the [AI4R gem](https://github.com/SergioFierens/ai4r) written and maintained by Sergio Fierens. While I cannot get into the specifics of the above mentioned project, I can tell you we used the Genetics Algorithm in the AI4R gem, specifically the GeneticSearch and Chromosome classes to solve our problem which in turn cut power consumption and eliminated idle running machinery.

What is great about AI4R is you don't need a PhD. in Computer Science to take advantage of AI in your apps. It was obviously developed with us "average" developers in mind. AI4R even gives you a specific example on how to solve the TSP with a nice example here.

Hope you find this Gem as useful as I have!