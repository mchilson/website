---
title: "Seeding your database in Rails - Part 2"
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/seeding-database.jpeg"
description: Using the seeds.rb file - Part 2
tags:
- Ruby
- Rails
- Database
- ActiveRecord
---

In the [first post about the seeds.rb file](/blogs/seeding-your-database-in-rails) we covered the basics of how the seeds.rb file works. In this post, we will be looking at practical examples of how to use the seeds.rb file in a production situation. There are several issues you may have to deal with using the seeds.rb file in a project. First is determining if your data you are about to add to the database already exists. Let look at how we can do this.

**first_or_create and find_or_create_by**
There are two methods in Active Record that can be helpful in this instance, they are *first_or_create* and *find_or_create_by*. Let's take a look at them both so you can decide which is more helpful to you in any given circumstance.

So now you are like, "Ok Mike, what is the difference between the two methods?" The difference between them is that *find_or_create_by* is accepting a hash of attributes and uses them to perform the search and creation.

```ruby
def find_or_create_by(attributes, &block)
  find_by(attributes) || create(attributes, &block)
end
```

Whereas, the *first_or_create* uses attributes only for the creation and it returns the first record from the provided scope.

```ruby
def first_or_create(attributes = nil, &block) # :nodoc:
  first || create(attributes, &block)
end
```
This makes it more useful in combination with various scopes and where clauses where the parameters from the where clause are passed to the creation. One other thing to note is that there is also bang equivalents *find_or_create_by!* and *first_or_create_by!* which raise an exception if the validation fails during the record creation.

first_or_create is sometimes misunderstood as people expect it to search by the attributes given, but that is not the case. For example:

```ruby
MyObject.first_or_create(attributes)
```

This will not search for a MyObject that satisfies the attributes. It will take the first My Object if any are present. It's useful if the conditions for finding are a subset of those used for creation.

```ruby
MyObject.where(something: value).first_or_create(attributes)
```

This will find the first MyObject where something: value. If none is present, it will use attributes to create it.

The first_or_create method is my personal favorite simply because it verbosely tells whoever is reading my seeds.rb file exactly what is going on. While you can really use either the name of this method fits its use here in the seeds.rb file better IMHO. Here is a short example of how to use the first_or_create method.

```ruby
rows = [
   {name: 'John Smith', employee_id: '0H221', city: 'Atlanta', state: 'GA'},
   {name: 'Beth Jones', employee_id: '0E57G', city: 'Buffalo', state: 'NY'},
   {name: 'Kim Hunt', employee_id: '0W117', city: 'Reno', state: 'NV'}
]

rows.each do |row|
  Employee.where(employee_id: row[:employee_id]).first_or_create(row)
end
```
The example code is pretty straightforward in that an array with the desired records is created and then a block that loops through the array rows checking to see if a value exists in the table. If the record exists it is skipped, otherwise, the record is created.

Well, that is about it! The sky is the limit as to what you can do in the seeds.rb file. You may want to clear out tables, etc. Not everything but most anything you can do in Rails you can do in this file to help initialize your data. If you have any specific questions please comment below or contact me here on my website. I hope you found these two short article helpful and you start to understand how to utilize the *seeds.rb* file more efficiently in your Rails projects.