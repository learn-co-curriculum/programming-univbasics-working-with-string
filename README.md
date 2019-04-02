# Title

## Learning Goals

* Recognize how to declare a `String` with double-quotes
* Recognize how to declare a `String` with single-quotes
* State the difference between single- and double-quoted `String`s
* Define _interpolation_
* Explain How Different Quote Characters Allow Flexibility
* Demonstrate escaping double-quotes in a `String`
* Join `String`s using `+`
* Identify why `TypeError` Happens When + `String` with Integer

## Introduction

Thus far in programming as conversation, we've really used numbers a lot. We
use numbers because they reach across language, culture, time itself.

But as we start writing more advanced programs, we want to say fun things like
`"Byon the poodle barks 10 times"`. These, occasionally silly, programs help us
get the grasp of programming. As a result, we need to learn a bit more about
the `String` type.

It's just like when we learned to talk, we learned to ask questions, make
statements, and communicate usefully, but as some point we were expected to
give our responses in full, proper sentences. So, let's learn how to format
Ruby's responses into meaningful `String`s.

## Recognize how to declare a `String` with double-quotes

We declare `String`s most often by putting them in double-quotes.

```ruby
greeting = "Hello, folks"
```

## Recognize how to declare a `String` with single-quotes

We can also declare `String`s most often by putting them in single-quotes.

```ruby
greeting = 'Hello, folks'
```

## State the difference between single- and double-quoted `String`s

The difference between single- and double-quoted `String`s is best seen when
using a special power of the `String`, _interpolating_ data.
 
### Define _interpolation_

When you use the _interpolation operator_ you take data from the programming
language and put it inside the `String`.  A double-quoted string allows `#{}`
to be treated as a special sign to Ruby that it should "plug in" a value. A
single-quoted string means, "Nope, don't _interpolate_."

```ruby
bark_count = 3
dq = "Byron barks #{bark_count} times" #=> Byron barks 3 times
sq = 'Byron barks #{bark_count} times' #=> Byron barks #{bark_count} times
```

## Explain How Different Quote Characters Allow Flexibility

What if you needed to store some dialog:

> "Wait," said Jo, "Do not go without me!"

Given the number of `"` used for direct speech, and the lack of _interpolation_
it might be a wise choice to use a single-quote here.

```ruby
little_woman_esque = '"Wait," said Jo, "Do not go without me!"'
```

## Demonstrate Escaping Double-quotes in a `String`

But what if you needed interpolation but also had embedded double-quotes? You
can "escape" the power of `"` to close a `String` by putting a `\` in front of
it:

```ruby
character = "Amy"
little_woman_esque = "\"Wait,\" said #{character}, \"Do not go without me!\""
```

## Join `String`s using `+`

Now here's an interesting use of the `+` operator when placed between
`String`s, it joins them and returns a ***new*** `String`.

```ruby
first_name = "Byronius"
clan_name = "Karbitus"
common_name = "Maris"

# With +
first_name + " " + clan_name + " " common_name #=> "Byronius Karbitus Maris"

# Or, with interpolation, like you already know
"#{first_name} #{clan_name} #{common_name}" #=> "Byronius Karbitus Maris"
```

## Identify why TypeError Happens When + String with Integer

Be careful, `+` only joins `Strings` with both sides are `String`

```ruby
fact = "Byron is "
tail = " years old"
age = 5

fact + age + tail #=> TypeError (no implicit conversion of Integer into String)
```

Ruby is not sure whether you want to add like an `Integer` (stored in `tail`)
or add like `String`s! If you need to do this, you should use _interpolation_:

```ruby
fact = "Byron is "
tail = " years old"
age = 5

fact + "#{age}" + tail #=> "Byron is 5 years old"

> **Alternate Approach**: Most types feature a _method_ called `.to_s` which tuns
> them into a String. You might remember the `.class` method we introduced when
> we were talking about type, earlier. `"Byron is " + 5.to_s + " years old."`
> works. We'll talk a lot more about methods later on, but you can explore this
> in IRB.

## Conclusion

With mastery of `String` we can use the expressions we've learned thus far to
make interesting programs using only expressions. We're going to provide an
example in the next lesson.
