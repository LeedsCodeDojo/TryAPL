Getting Started Exercises
=========================

#### 1. Basic Operators

You can use the standard operators as normal, e.g.

        5 - 2
    3

###### Ex 1.1 - Add two numbers together.

One difference between APL and other languages is that you use the standard maths operators, e,g, 'x' instead of '*' for multiplication.  This means expressions in APL are more similar to their mathematical descriptions - but it does mean you can't enter them with a conventiona keyboard..

###### Ex 1.2 - Multiply two numbers.

#### 2. Arrays

APL operators also work with arrays as standard.  To make an array, simply put spaces between the elements:

    1 2 3 4

Arrays can contain elements of different types, but we'll stick to numbers for now.

With arrays of the same size, operators work on pairs of elements:

        5 6 7 - 1 2 3
    4 4 4

###### Ex 2.1: Find the results of adding 10+1, 20+2 and 30+3 in a single operation.

If you apply a single value to an array, the operation will apply to each element separately:

        1 + 2 3 4
    3 4 5

If you want to reduce the array down to a single value, you'll need the reduce operator '/' which can be combined with most normal operators:

        +/ 1 2 3
    6

###### Ex 2.2: Calculate !5 (5 factorial - 1x2x3x4x5) using the reduce operator.

Instead of writing out lists of numbers, you can generate sequences with ⍳:

        ⍳10
    1 2 3 4 5 6 7 8 9 10
    
###### Ex 2.3 Calculate !5 (5 factorial - 1x2x3x4x5) using the ⍳ operator.

Of course, you could just do !5..

#### 3. Variables

Assigning variables is easy with ←:

        x←1
        x
    1

###### Ex 3.1 Assign an array containing the first ten numbers to the variable x

#### 4. Functions

You can create functions inline similar to the way you assign variables.  For example, we can create a niladic function (taking no arguments):

    nilf←{3+5}
    
To create a function that takes an argument (a monadic function), you need to use the ⍵ character to represent the argument:

        add5←{5+⍵}
        add5 3
    8

You can only create single-argument functions in this way, although like everything else the argument can of course be an array.

###### Ex 4.1 Create a function that doubles the passed value.

You can create functions that take two arguments (dyadic functions) using the ⍺ and ⍵ characters to represent the left and right-hand arguments respectively:

        minus←{⍺-⍵}
        5 minus 3
    2

As in other cases, the arguments can be arrays:

        5 6 7 minus 1 2 3
    4 4 4
    
        5 6 7 minus 1
    4 5 6
    
        5 minus 1 2 3
    4 3 2
  
You can even use your new function with the Reduce operator:

        minus/100 50 10
    60
    
(Was 60 the value you expected?  Can you explain it?  See the next section for details.)

###### Ex 4.2 Create a function that multiplies two values.

#### 5. Evaluation order

Unlike most languages, APL evaluates everything strictly right-to-left, there's no operator precedence:

        10×3+2
    50
    
Reduction also happens right-to-left, hence the perhaps unexpected result in Part 4.

As with most languages, you can use parenthesis to define an explicit order:

        (10×3)+2
    32
    
###### Ex 5.1 Calculate (5×5+5)÷2-3, which should equal 12, in the fewest characters you can.

Note: If you want a negative number, you need to use a 'high minus', e.g. ¯1.
