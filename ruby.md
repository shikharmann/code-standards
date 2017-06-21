# Ruby & Rails Code Standards

## Table of Contents
* [Indentation](#indentation)
* [Predicate Methods](#predicate-methods)
* [Iteration](#iteration)
* [Conditionals](#conditionals)
* [Symbols](##symbols)
* [Time](##time)
* [Comments](##comments)
* [Whitespace](#whitespace)
* [Naming](#naming)
* [Classes & Modules](##classes-and-modules)
* [Tags](#tags)
* [Exceptions](##exceptions)

## Indentation
Although the most widely adapted and agreed upon style guidelines in the Ruby community is to use 2 space indentation, we  use **4 space indentation** for the sake of consistency.  

## Predicate Methods
Define predicate methods with `?` and keep inline with idiomaticness and readability of Ruby.
For example: `object.valid?` or `fee.paid?`

Methods that don't return a boolean, shouldn't end in a question mark

## Iteration: 
Use `each` instead of `for`.

```
  (1..100).each do |i|
    ...
  end
```

## Conditionals
Use `unless` instead of `!if`.

```
  unless true
    do_this
  end
```

Again, it’s about readability. However, if you need to involve an `else` to your conditional, never use `unless-else`.

```
<!-- Not recommended -->
  unless user.save
    #throw error
  else
    #return success
  end
```

Use `case/when` conditionals instead of lengthy if statements

Use double bang (`!!`) to determine if a value exists
```
  def has_middle_name?
    !!@middle_name
  end
```

## Symbols
Use symbols instead of strings in hashes. Symbols are similar to strings, except they are immutable and are used to name variables. They should be used whenever you are storing the name of something that does not have to be mutated. They are more efficient than strings because they are stored in one spot in memory.

## Time
Use `Time.zone.now` instead of `Time.now`. The ActiveSupport method `Time.zone.now` should be used in place of the Ruby method `Time.now` to pickup the local time zone.

## Comments
Write self-documenting code . Ruby/Rails provides a lot of magic codes, especially for metaprogramming, they are powerful, less codes to implement more functions, but they are not intuition, you should write good comment for your magic codes.
Avoid superfluous comments.

```
  # bad
  counter += 1 # Increments counter by one.
```

## Whitespace
Trailing whitespace always makes noises in version control system, it is meaningless. We should remove trailing whitespace to avoid annoying other team members.

## Naming
* Use `snake_case` for symbols, methods and variables.
```
  # bad
  :'some symbol'
  :SomeSymbol
  :someSymbol

  # good
  :some_symbol
```
* Do not separate numbers from letters on symbols, methods and variables
```
  # bad
  :some_sym_1

  # good
  :some_sym1
```

* Use CamelCase for classes and modules
```
  # bad
  class Someclass
    # some code
  end

  # good
  class SomeClass
    # some code
  end
```

* Use `snake_case` for naming files and directories.
* Use `SCREAMING_SNAKE_CASE` for other constants.


```
  # bad
  SomeConst = 5

  # good
  SOME_CONST = 5

```

## Classes & Modules
* Use a consistent structure in your class definitions
* Split multiple mixins into separate statements.
* Don't nest multi-line classes within classes. Try to have such nested classes each in their own file in a folder named like the containing class.
* Avoid the use of `attr`. Use `attr_reader` and `attr_accessor` instead
* Avoid the usage of class (@@) variables due to their "nasty" behavior in inheritance.
* Use def self.method to define class methods. This makes the code easier to refactor since the class name is not repeated.

## Tags
Avoid using HTML tags and use Rails tags instead. 

```
  <!-- Not recommended -->
  <a href="/edit">Edit</a>

  <!--Recommended -->
  <%= link_to edit_campaign_type_path(:id => ctype.id) %>

```

## Standard Error
* Don't rescue Exception, rescue StandardError.
* Prefer `raise` over `fail` for exceptions.
