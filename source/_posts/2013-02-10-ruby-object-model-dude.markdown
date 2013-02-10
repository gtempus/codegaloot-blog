---
layout: post
title: "Ruby Object Model: Methods"
date: 2013-02-10 15:29
author: Gary Tempus
comments: false
categories: [metaprogramming, ruby]
---
Ruby methods belong to the classes that define them. This makes sense since instantiations (objects) of the class inherit the same methods.

I thought I would share some method discoveries as I continue on my exploration of Ruby's object model. My idea is to elaborate on these things later on (in updates or later posts). Right now I'm interested in capturing what I'm learning...

``` ruby
class AnyClass
  def any_instance_method
    'Nobody here but us chickens!'
  end
end

AnyClass.methods.grep /new/	# => [:new]
anyObj = AnyClass.new 		# => #<AnyClass:0x...>

# passing false as an argument means don't include inherited methods
AnyClass.methods.grep /any/    	 # => []
AnyClass.instance_methods false	 # => [:any_instance_method]

anyObj.methods(false) 	       # => []
anyObj.methods.grep /any/      # => [:any_instance_method]
anyObj.instance_methods	       # => NoMethodError!
anyObj.methods.grep /new/      # => []
```
So what's the big deal? Well, it highlights an important distinction.
Line 7 says that `new` is a class method and I call it on line 8 to create the `anyObj` instance of `AnyClass`. Notice that the method call in line 11 that looks for a method containing `any` returns an empty array. So, now we know that `any_instance_method` is not a class method of `AnyClass` (i.e. I can't call `AnyClass.any_instance_method`).

Instead, and this is the distinction, we see that `any_instance_method` is an *instance* method that can be only called by instantiations of the `AnyClass` (line 12).

Finally, `anyObj` reveals that it doesn't define any of it's own methods but instead inherits them from `AnyClass` (line 14 & 15). We see that indeed instances of a class do not contain methods; just their instance variables as discussed on my previous post. Furthermore, you can't instantiate an object from an object as I found out on line 16 and 17.