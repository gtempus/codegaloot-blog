---
layout: post
title: "Where Are My Instance Variables?"
date: 2013-02-09 19:58
author: Gary Tempus
comments: false
categories: [ruby, metaprogramming] 
---

Head's up. There is no connection between a ruby class and its instance variables. My java brain finds this very interesting. Instance variables can vary from object to object of the same class. They just pop into existence once you assign them a value. Cool!

``` ruby
class AnyClass
  def any_method
    @var = 1
  end
end

obj1, obj2 = AnyClass.new, AnyClass.new

obj1.any_method
obj1.instance_variables  # => [:@var]

obj2.instance_variables  # => []
```

