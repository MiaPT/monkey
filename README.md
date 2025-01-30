# Monkey Interpreter :\)

This is my implementation of the Monkey programming language, following the book _Writing an Interpreter in Go_ by Thorsten Ball.


# My Additions

### added GTE (`>=`) and LTE (`<=`) operators
because why not

### added support for reassigning variables and array elements, and reassigning/adding hashmap elements
In Monkey, you cannot reassign variables*, array elements or hashmap elements, or add to a hashmap. But it felt weird to be able to do that, so I decided to add it.
```
>> let myList = [1,2,3]
>> myList[0] = 5
>> myList
[5,2,3] 

>> let myHash = {"a": 1, "b": 2}
>> myHash["a"] = 5
>> myHash["c"] = 3
>> myHash
{"a": 5, "b": 2, "c": 3}
```
\* not entirely true - you can reassign a variable, but only with a new let statement

Because reassingment is built like an infix expression, and to smoothly integrate it into the existing implementation, it is an expression and not a statement. This allows for code like this:
```
>> let a = 5
>> let b = a = 10
>> a
10
>> b
10
```


