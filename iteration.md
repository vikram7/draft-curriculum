## Iteration

With a basic data structure like an array, we might want to sum up all the values of an array. Maybe we want to modify all the values of a hash. Perhaps we want to extract each nested value of a compound data structures. Ruby comes built into the language some excellent methods that allow us to parse through these kinds of data structures to extract exactly what we need.

We call doing a repeated action on a data structure *iteration*. We can *iterate* over an array to print out all the array's values. We can *iterate* over an array to sum up all the values in the array. We can *iterate* over an array to sum up all the squares of the values of an array.

Similarly, we can *iterate* over a hash to print out all the values of the keys. We can *iterate* over a hash to print out each of the key-value pairs in a specific type of format. We can *iterate* over a hash to change the each of the values of the hash.

Sounds pretty convenient, right? It is. So what do these iteration methods look like?

You might have come across [looping](http://www.ruby-doc.org/docs/Tutorial/part_02/loops.html) methods like [**for**](http://www.dotnetperls.com/while-ruby), [**while**](http://www.ruby-doc.org/docs/Tutorial/part_02/while.html), or [**until**](http://www.dotnetperls.com/while-ruby) in your reading. These are built in methods that allow us to do repeated tasks over a set period of time or number of iterations or until some criteria is hit. Every language has their own loop methods, but Ruby in particular has a large suite of iterators, which make for incredibly short and elegant code. Take a look at the [Enumerable](http://ruby-doc.org/core-2.2.0/Enumerable.html) docs for a list of these methods available to you as a Rubyist.

