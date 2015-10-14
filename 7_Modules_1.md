####Modules

```ruby
module GoodNight
  def leaving
    puts "Goodnight, I had a great time!"
  end

  def guest_leaving
    puts "Goodnight, Thank you for coming!"
  end
end
```

You can think of a module as a container/file/box that stores methods. (Whatever analogy works for you.)


Modules are very much like classes. In fact the only difference is that we can't make new modules with the new method.

For example: `Goodnight.new` isn't allowed and doesn't do anything.

Modules typically contain constants and/or methods.

####Constants

```ruby
module SalesGoals
MINIMUM_QUOTA = 25

  def success
    puts "You've reached your goal for the week."
  end

  def try_harder
    puts "You didn't reach the minimum quota this week."
  end
end
```

A constant is a defined in all capital letters. It is a like a variable in that it stores a value. The difference is that the value does not change once it is assigned.

Technically you _can_ change it but if you do Ruby will warn you.

Copy the constant into irb.
```ruby
MIMIMUM_QUOTA = 25
```
Now, reset it to 35. Notice the warning Ruby throws at you. It will change the constant but gives you plenty of notice in case you accidentally changed it and want to set it back to what it was right away.



Now let's create a new class to use a method from our module.  Here we've created a Sales Associate class.

```ruby
class SalesAssociate
  include SalesGoals
end
```

Notice that it is empty except to include the `SalesGoals` module. We're going to use this class in a few minutes but first lets create another module. You can use multiple modules inside a class so lets practice that.

```ruby
module SalesHistory

def august
  puts "You met your sales quota 4/4 weeks!"
  end

  def september
  puts "You met your sales quota 2/4 weeks!"
  end
end

```

Now lets add that to our SalesAssociate class as well.

```ruby
class SalesAssociate
  include SalesGoals
  include SalesHistory
end
```

Now the `SalesAssociate` is able to utilize the method inside the SalesGoals module *as well* as the methods inside the SalesAssociate module.

Now lets instantiate an actual SalesAssociate.
```ruby
Joe = SalesAssociate.new
```

Let's try the methods from our modules and see if they work.

```ruby
Joe.august
Joe.success
Joe.september
Joe.try_harder
```
These will work because we included them in our class!

When we use a module this way its often called a mixin. We are taking a class and mixing in methods from the module. Please go on to the next lesson for more *very important* information on modules.
