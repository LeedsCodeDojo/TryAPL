Getting Started Exercises
=========================

You can use the standard operators as normal, e.g.

        5 - 2
    3

##### Ex 1.1 - Add two numbers together.

One difference between APL and other languages is that you use the standard maths operators, e,g, 'x' instead of '*' for multiplication.  This means expressions in APL are more similar to their mathematical descriptions - but it does mean you can't enter them with a conventiona keyboard..

##### Ex 1.2 - Multiply two numbers.

APL operators also work with arrays as standard.  With arrays of the same size, operators wrk on pairs of elements:

        5 6 7 - 1 2 3
    4 4 4

##### Ex 1.3: Find the results of adding 10+1, 20+2 and 30+3 in a single operation.

If you apply a single value to an array, the operation will apply to each element separately:

        1 + 2 3 4
    3 4 5

If you want to reduce the array down to a single value, you'll need the reduce operator '/' which can be combined with most normal operators:

        +/ 1 2 3
    6

#### Ex 1.4: Calculate !5 (5 factorial - 1x2x3x4x5) using the reduce operator.

Instead of writing out lists of numbers, you can generate sequences with ⍳:

        ⍳10
    1 2 3 4 5 6 7 8 9 10
    
#### Ex 1.5 Calculate !5 (5 factorial - 1x2x3x4x5) using the ⍳ operator.
