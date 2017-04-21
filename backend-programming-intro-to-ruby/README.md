# Intro to Ruby

## Ruby in your Terminal

To start an interactive Ruby session, go on your console and type:

`$ irb`

**What is a REPL?**
You will enter in what is called a REPL specific to Ruby. REPL stands for Read-Eval-Print Loop. It is an environment that takes a user input (read), interprete it (eval) and return the result to the user (print) and do it each time the user asks to do it (loop).

## Basic Data Types

We're going to first learn about 4 basic types of objects in Ruby:
- `Integer`: whole number (eg: 1)
- `Float`: a decimal number, higher precision (eg: 21.356)
- `String`: a single character or group of them (eg: "hello world")
- `Nil`: an uninitialized, undefined, or empty value

Try the following:

`> 3 + 2`

`> 3 * 2.25`

`> 3 / 2`

**What is interesting about the result of 3 / 2?**

`> 3 ** 2`

`> Math.sqrt(9)`

**What is an object and what is OOP?**
Have you tried `Math.sqrt(9)`. Math is what is called an Object and `.sqrt()` a Method. An object is a data structure that contains **properties** and **methods**.
A method is a function. Some methods are already built in ruby (like sqrt()) but you can also build some yourself!

Enter the next two commands:

`> a = 4 * 3`

`> b = 6 + 2`

**What is a variable?**

Try the following:

`> temp_val = a + b`

`> puts temp_val`

`> temp_val = a * b - temp_val`

`> puts temp_val`

## Functions

Let's build our first program! We are going to build a function. A function looks like this:

 `def name-of-your-function(parameter1, parameter2,....)
    your code
  end
 `

Here is an example:

```ruby
def say_hello(name)
  puts "Hey " + name.capitalize + "!"
end
```

## Basic Logic

Next, let's get familiar with some basic logic:
- Booleans: `true` / `false`
Booleans only return 2 values: True or False. For example:
`3 > 4 ==> FALSE`
`4 > 3 ==> TRUE`
`3 > 3 ==> FALSE`

- Control statements: `if`/`elsif`/`else`
Control statements execute an action if this action is true. For example

```rb
if your_age < 40
  puts "you are not older than 40 years old"

elsif your_age < 50
  puts "you are older than 40 but not older than 50"

else
  puts "You are older than 50"
end
```

Now every number you set in your variable can be handled by your code.

##### Comparison Operators:

- `==`: Checks whether the value of two operands is equal. If yes, evaluates to true, if no, evaluates to false
- `!=`: Checks whether the value of two operands ARE NOT equal. If yes, evaluates to true, if no, evaluates to false
- `>`: Checks if operand on left is greater than operand on right. If yes, evaluates to true, if no, evaluates to false
- `<`: Less than

```ruby
def milk_is_expired?(days_old)

  result = ""

  if days_old < 5
    result = "No!"    
  elsif days_old < 12
    result = "Not yet."
  elsif days_old < 16
    result = "Maybe. Smell test first!"
  else
    result = "Yes."
  end

  return result
end
```

# Advanced Data Types

##### Array
Ordered lists of data are important. Let's get familiar with `arrays`:
- Array: a zero-indexed ordered series of values. (eg: [1, 2, 3, 4])

Try the following:

`> my_array = ["Min", "Ashmeet", "Adam", "Anastasia", "Constantine", "Lauren"]`

`> my_array[0]`

`> my_array[200]`

**How do we access "Lauren"?**

Common array methods:
- `.count`: `my_array.count`
- `.first`: `my_array.first`
- `.last`: `my_array.last`
- `.push`: `my_array.push("Jarad")`

**How can we look at all the items in an array without explicitly accessing each index?**
- `.each`
```ruby
  my_array.each do |array_item|
    puts array_item
  end
```

##### Hash

Accessing data quickly is important. How can we access a piece of data without looking through an entire array? With Hashes.

- Hashes are a collection of key value pairs.

try the following:

`casey = {age: 31, height: 5.8, occupation: "web developer"}`

`casey[:age]`

**How can we access Casey's occupation?**

**How can we add another attribute to Casey?**

`casey[:location] = "San Francisco"`
