!SLIDE subsection
# Introduction to Ruby for Programmers

<img src="img/ruby-logo.jpg" width="250">

!SLIDE

### Ruby is a Language
<img src="img/ruby-logo.jpg" height="250" width="250">

### Rails is a Framework
<img src="img/rails_logo.jpg" height="250" width="250">

!SLIDE

"People want to express themselves when they program."

"They don't want to fight with the language."

"Programming languages must feel natural to programmers."

"I tried to make people enjoy programming and concentrate on the fun and creative part of programming when they use Ruby."

&nbsp;- Matz (Yukihiro Matsumoto)

!SLIDE 

### Ruby 1.0 released in 1996
### open source 

!SLIDE bullets

## Ruby Language Overview
* Dynamically typed
* Interpreted
* Can be modified at runtime
* Object oriented
* Blocks & lambdas
* Perl-like Regular Expressions

!SLIDE

Let's get started

!SLIDE

# IRB: Interactive RuBy

!SLIDE

    @@@ ruby
    >> 4
    >> 4 + 4

!SLIDE

# Everything is an object

!SLIDE

    @@@ ruby
    “test”.upcase
    “test”.class
    “test”.methods

!SLIDE

# Everything evaluates to something

!SLIDE

    @@@ ruby
    2 + 2
    (2+2).zero?

!SLIDE

# Methods are messages

!SLIDE

    @@@ ruby
    thing.do(4)
    thing.do 4
    thing.send "do", 4

!SLIDE

# Operators are Methods

!SLIDE

    @@@ ruby
    1 + 2
    1.+(2)
    1.send "+", 2

!SLIDE

    @@@ ruby
    # is a comment

!SLIDE

Ruby aims to be elegant and readable

so punctuation and boilerplate are minimal

!SLIDE

# You don't need semicolons
 
!SLIDE

# Use parens when you need them
   
!SLIDE

    @@@ ruby
    >> "Hello".gsub 'H', 'h' 
    => "hello"

    >> "Hello".gsub("H", "h").reverse 
    => "olleh"

!SLIDE subsection

# Variables, symbols, constants

!SLIDE

## :this_is_a_symbol
There is only one representation of a given symbol in memory, so it really
means "the thing named :this_is_a_symbol" to the ruby interpreter. 
In ruby,
we prefer symbols over hardcoded globals or strings. They're very lightweight.

!SLIDE

# Collections

!SLIDE

Arrays are sized dynamically and can be of mixed types.
 
!SLIDE

    @@@ ruby
    a = [1, 2, 3]
    a.push "four" #=> [1, 2, 3, "four"]
    a.pop #=> "four"
    a[0] #=> 1

!SLIDE

Hashes are like an associative map

!SLIDE

    @@@ ruby
    states = {"MA" => "Massachusetts", 
              "CA" => "California"}
    states["MA"]

!SLIDE

    @@@ ruby
    my_hash = {:a_symbol => 3, "a string" => 4}
    my_hash[:a_symbol] 
    => 3

!SLIDE

# String interpolation

    @@@ ruby
    "string #{2 + 2} string"
    => "string 4 string"

Any Ruby code can go inside the braces

It gets evaluated and stuck inside the string

!SLIDE

    @@@ ruby
    >> a = "world"   
    >> puts "hello #{a}"
    hello world
    
    >> a = 2
    >> puts "hello #{a}"
    hello 2
    
    >> a = nil
    >> puts "hello #{a} there"
    hello  there


!SLIDE

# Iteration

!SLIDE

    @@@ ruby
    my_array = ["cat", "dog", ”world"]
    my_array.each do |item|
      puts "hello " + item
    end

!SLIDE

    @@@ ruby
    my_hash = { :type => "cat", 
                :name => "Beckett", 
                :breed => "alley cat" }
    my_hash.each do |key, value|
      puts "My " + key.to_s + " is " + value
    end


!SLIDE

Classes and methods

!SLIDE

    @@@ ruby
    class Thing
      def return_something
        "something"
      end
    end

!SLIDE

    @@@ ruby    
    class Thing
      def do_something(a,b)
        a + b 
      end
    end


!SLIDE

    @@@ ruby
    var 
    @var
    @@var
    $var
    VAR

!SLIDE

    @@@ ruby
    var   # could be a local variable
    @var  # instance variable
    @@var # class variable
    $var  # global variable
    VAR   # constant
    
!SLIDE

Methods can take blocks, which are like anonymous functions.

!SLIDE

    @@@ ruby
    my_array = ["cat", "dog", ”world"]
    my_array.each do |item|
      puts "hello " + item
    end

!SLIDE

    @@@ ruby
    def do_something
       yield
    end

!SLIDE

    @@@ ruby
    [1, 2, 3].each do |item|
       puts "#{item} is #{item.even? ? "even" : "odd"}."
    end
 
!SLIDE

Blocks can also return a value. Map translates each item in an array.
 
!SLIDE

    @@@ ruby
    >> ["hello", "world"].map{ |string| string.upcase } 
    => ["HELLO", "WORLD"]
 
!SLIDE subsection

# more neat things about ruby

!SLIDE

## duck typing
 
!SLIDE

    @@@ ruby
    def print_even_or_odd(array_like_thing)
      array_like_thing.each do |item|
        puts "#{item} is #{item.even? ? "even" : "odd"}."
      end
    end
 
!SLIDE

    @@@ ruby
    print_even_or_odd [1, 2, 3]
    print_even_or_odd 1..3
 
!SLIDE

#### advanced ruby 
 
!SLIDE

#### meta-programming
#### creating Domain-Specific Languages (DSLs)

!SLIDE

#Rails
#Rake
#Cucumber
#Rspec
#etc

!SLIDE

    method_missing

!SLIDE

#### private vs public 

!SLIDE

####Private really just means "please don't come in." 
####&nbsp;
####If someone has access to your runtime environment, they are trusted.
####&nbsp;
####Spend your time writing code (and testing it), not protecting yourself from other programmers.
 
!SLIDE

    @@@ ruby
    class Fixnum
      def even?
        self % 2 == 0
      end
    end
    
    1.even? #=> false

!SLIDE

#### everything is an object

!SLIDE

#### Classes are objects
####&nbsp;
#### class methods are really just methods on the class object. 
####&nbsp;
#### Code evaluated in the scope of a class definition acts on the class object.

!SLIDE

# Ruby Quickstart for Refugees

<https://gist.github.com/190567>
 
    --
 
    # is a comment.
    You don't need semicolons.
    Ruby aims to be elegant and readable, so punctuation and boilerplate are
    minimal.
 
    --
 
    Ruby is truly object-oriented. Everything is an object.
 
    1.to_s #=> "1"
 
    --
 
    You don't need parens if the statement is unambiguous:
    "hello".gsub 'h', 'H' #=> "Hello"
 
    But they are needed if the statement is ambiguous:
    "olleh".gsub("h", "H").reverse #=> "Hello"
 
    --
 
    Classes can be reopened at any time, by anyone with access to the interpreter.
 
    class Fixnum
      def even?
        self % 2 == 0
      end
    end
 
    1.even? #=> false
 
    --
 
    Literal Types:
 
    Symbols look like :this_is_a_symbol
    There is only one representation of a given symbol in memory, so it really
    means "the thing named :this_is_a_symbol" to the ruby interpreter. In ruby,
    we prefer symbols over hardcoded globals or strings. They're very lightweight.
 
    Hashes (much like an associative map) look like
    my_hash = {:a_symbol => 3, "a string" => 4}
    We reference hashes like
    my_hash[:a_symbol] #=> 3
 
    Arrays use the familiar [a, b, c] format. Arrays are sized dynamically and
    can be of mixed types.
 
    a = [1, 2, 3]
    a.push 4 #=> [1, 2, 3, 4]
    a.pop #=> 4
    a[0] #=> 1
 
    Strings
 
    We use "string #{ruby code} string" for String interpolation.
 
    def declare_fun(string)
      "I think that #{string} is fun!"
    end
 
    declare_fun "ruby" #=> "I think that ruby is fun!"
 
    --
 
    Methods can take blocks, which are like anonymous functions.
    [1, 2, 3].each do |item|
      puts "#{item} is #{item.even? ? "even" : "odd"}."
    end
 
    This takes each item in the array, assigns it to the variable "item", and
    prints whether it's even.
 
    --
 
    Blocks can also return a value. Map translates each item in an array.
 
    ["hello", "world"].map{ |string| string.upcase } #=> ["HELLO", "WORLD"]
 
    --
 
    Ruby uses duck typing, which means we don't care what an object is as long as
    it does what we want to do with it.
 
    def print_even_or_odd(array_like_thing)
      array_like_thing.each do |item|
        puts "#{item} is #{item.even? ? "even" : "odd"}."
      end
    end
 
    print_even_or_odd [1, 2, 3]
    print_even_or_odd 1..3 # a Range object, which also responds to each
 
    --
 
    Advanced topics that are worth discussing if you're interested:
 
    Ruby provides really powerful tools for meta-programming (writing code that
    writes code on the fly) and introspection. This is most of the magic of Rails.
 
    Ruby lets you handle undefined method calls at the source with a "catcher"
    method called method_missing. This is the entry point for a lot of powerful
    stuff.
 
    Ruby has a mixin-based inheritance system that is somewhat like multiple
    inheritance with one primary ancestor class.
 
    Ruby doesn't provide much protection from other programmers. Private really
    just means "please don't come in." The ruby philosophy is that if someone has
    access to your runtime environment, you should make sure they're trusted.
    Spend your time writing code, not protecting yourself from other programmers.
 
    Classes are objects, and class methods are really just methods on the class
    object. Code evaluated in the scope of a class definition acts on the class
    object.


