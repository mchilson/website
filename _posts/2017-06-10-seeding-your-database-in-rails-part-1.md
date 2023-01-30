---
title: "Seeding your database in Rails - Part 1"
layout: post
post-image: "https://mikechilson-blog-assets.s3.amazonaws.com/seeding-database.jpeg"
description: Using the seeds.rb file - Part 1
tags:
- Ruby
- Rails
- Database
- ActiveRecord
---

When writing applications in Rails that use databases (as most do), we often have the need to populate small "reference" tables with data (like credit card types, colors, dog breeds, categories, etc) used in form drop-downs, test data when developing or inserting specific records into the database at deployment time. This is accomplished in Rails with the seeds.rb file located in the DB directory of your rails project folder. Surprisingly, most new Rails developers do not know about this file. If you open the file seeds.rb file in Rails 5.x you will see some examples of how you insert records. Here is what you will see:

```Ruby
# This file should contain all the record creation needed to seed 
# the database with its default values.
# The data can then be loaded with the rails db:seed command 
# (or created alongside the database with db:setup).
#
# Examples:
#
# movies = Movie.create([{ name: 'Star Wars' }, { name: 'Lord of the Rings' }])
# Character.create(name: 'Luke', movie: movies.first)
```

You can simply create the records individually like this in the seeds.rb file:

```Ruby
CreditCard.create("name"=>"Visa", "image"=>"visa.png")
CreditCard.create("name"=>"Mastercard", "image"=>"mastercard.png")
CreditCard.create("name"=>"American Express", "image"=>"amx.png")
```

As you can see there is nothing magical about the seeds.rb file. It's just a ruby file that you can run code to seed the database just like you can in the Rails Console. You can use it for test data while developing. Here is a simple example of adding some test data to my skills model using a block:

```Ruby
5.times do |skill|
  Skill.create!(
    title: "Rails #{skill}",
    percent_utilized: 20
  )
end
puts "Skills records seeded"
```

See, nothing to it! One note here. If you are going to upload your code to a public repository (like GitHub or Bitbucket) DO NOT ADD USER ACCOUNT INFORMATION TO YOUR SEEDS.RB FILE.

So once you get your seeds.rb file built you can populate the data using the command:

```Ruby
rails db:seed
```

If you want to learn more about the seeds.rb file. Here are some references you can check out.

[Active Record Migrations](http://edgeguides.rubyonrails.org/active_record_migrations.html)

[Seeding a database using the Rails command line](https://davidmles.com/seeding-database-rails/)

[Faker Gem](https://github.com/stympy/faker)

[Populator Gem](https://github.com/ryanb/populator)

Part two of this article.
[Seeding your database in Rails - Part 2](http://www.mikechilson.com/blogs/seeding-your-database-in-rails-part-2)