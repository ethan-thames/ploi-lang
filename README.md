# ploi-lang

## Synopsis

Ploi is a programming language based on [Build Your Own Lisp](http://buildyourownlisp.com/). Ploi, my take on BYOL, has elements that make it more readable and approachable to non-Lisp programmers (Like me!). It uses Python-style lists, and has a minimal set of builtins, so most functionality comes from the standard library, which ~~steals~~ borrows functions from the Haskell Prelude.

## Code Example

```python
(define [proc] (lambda [name args body] # Procedure to ease the creation of procedures
    [define (name) (lambda (args) body)]
  )
)

(proc [andor] [x y] # Either or both of x and y are true
    [if (< (+ x y) 1)
        [0]
        [1]
    ]
)

(proc [fib-nth] [num] # Find the nth Fibonacci Number
    [if (andor (== num 1) (== num 2))
        [1]
        [+ (fib-nth (- num 1)) (fib-nth (- num 2))]
    ]
)

(print (fib-nth 7)) # Print the 7th Fibonacci Number

```

## Name

The name, ploi, stands for Powerful List Operation Interpreter. 

## Installation

I haven't written a Makefile yet, you'll have to compile it yourself.
```sh
git clone https://github.com/LambdaProgrammer/ploi-lang.git
gcc --std=c99 ploi.c mpc.c -lm -ledit -o ploi
```

## Builtins

There are 34 builtin procedures. Here's a list of all of them.

|Name|Use|
|:-:|:-:|
|`lambda`|Return a lambda function|
|`define`|Define a global variable|
|`put`|Define a local variable|
|`head`|Get the first calue of a list|
|`tail`|Get all but the first value of a list|
|`eval`|Evaluate a list as a S-Expression|
|`join`|Preappend value(s) to a list|
|`+`|Add|
|`-`|Subtrace|
|`*`|Multiply|
|`/`|Divide|
|`%`|Modulo|
|`^`|Power|
|`assert`|Raise and error if a condition is not 1|
|`if`|Conditional|
|`==`|Equal|
|`!=`|Not Equal|
|`>`|Greater Than|
|`<`|Less Than|
|`>=`|Greater than or equal to|
|`<=`|Less than or equal to|
|`imports`|Load the contents of a file|
|`throw`|Throw an error|
|`print`|Print args with no newline between|
|`println`|Print args with a newline between|
|`input`|Get textual user input|
|`exit`|Exit with a error code|
|`argc`|Get the number of command line arguments|
|`argv`|Get a list of command line arguments|
|`Integer`|Convert to a Integer|
|`Double`|Convert to a Double|
|`List`|Return a list of the arguments|
|`type`|Get the type of a input as a string|

## Contributors

I would be very happy if you would contribute. I am a very new C programmer, so I need ~~lots of~~ some help.

## License

Ploi is published under the [zlib/libpng license](https://www.tldrlegal.com/l/zlib)
