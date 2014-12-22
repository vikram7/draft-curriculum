## Simple Data Structures

### Arrays
Arrays are great. You've probably come across them in the prework, but here's a quick review.

Arrays represent an ordered list of some set of data. The data can be of any type: integer, strings or even a mix of data types. An array can contain other arrays too. Ok, so what do they look like? Say we had a list of bank transactions representing a checking account:

```
deposit $500
withdraw $200
withdraw $250
deposit $400
withdraw $12
deposit $500
withdraw $8
withdraw $90
withdraw $15
```

How could you implement an array to represent this set of transactions? Like this:

```ruby
transactions = [500, -200, -250, 400, -12, 500, -8, -90, -15]
```

Now we have a `transactions` array. We can do all kinds of fun things on this array with Ruby. Because we have an ordered list, we can call the `n`th transaction on this array. Arrays start with an index of `0` so to get the first transaction of this list, we would call `transactions[0]`. We can also call `transactions.first`, which returns the same value (unfortunately, there is no `transactions.second` or `transactions.third`, but there is a `transactions.last` which returns the last value of an array).

```ruby
transactions = [500, -200, -250, 400, -12, 500, -8, -90, -15]
=> [500, -200, -250, 400, -12, 500, -8, -90, -15]

transactions[0]
=> 500

transactions.first
=> 500

transactions.last
=> -15

```

How would you get the third transaction?

```ruby
transactions[2]
=> -250
```

What about the fifth transaction?

```ruby
transactions[4]
=> -12
```

So those aren't too bad. How would you go about getting the last value of `transactions`? You could use `transactions.last` but let's put that aside for a second. There are two other ways to go about it. The first way, is to count, starting from `0` to the end of the array, or in this case, `8`. The other way is to note that the end of an array begins with an index of `-1`, or `transactions[-1]`. This number decreases by `1` the further left you go, so the second from the last would be `transactions[-2]` and third from the last would be `transactions[-3]`, and so forth and so on.

Let's take a look at these examples then:

```ruby
transactions.last
=> -15

transactions[-1]
=> -15

transactions[-2]
=> -90

transactions[-3]
=> -8
```

See the [Ruby docs](Link to ruby docs) about other methods the Array class has available to it.

### Hashes

What's a hash? In short, it's a collection of key-value pairs. What's a key value pair?


### Drill manipulating a hash

Say we have a data structure that stores information about people's phone numbers:


```ruby
phone_numbers = {
  'Dan'   => '508.555.5555',
  'Jenny' => '508.867.5309',
  'Sam'   => '508.777.7777'
}
```

#### Access a value

First of all, how would we access Dan's phone number?

```ruby
phone_numbers['Dan']
```

#### Iterate over the hash

How would we print out each person's name next to their phone number, like so:

```no-highlight
Dan: 508.555.5555
Jenny: 508.867.5309
Sam: 508.777.7777
```

```ruby
phone_numbers.each do |name, number|
  puts "#{name}: #{number}"
end
```

### Adding numbers to the hash

Say we want to keep track of multiple phone numbers.  For each person, we want to track both home phone and cell phone.

```ruby
phone_numbers = {
  'Dan'   => ['508.555.5555', '508.555.6666'],
  'Jenny' => ['508.867.5309', '508.697.5555'],
  'Sam'   => ['508.777.7777', '508.946.3214']
}
```

Let's say that the first number is the name's home number, while the second number is their mobile number.

#### Questions

**Launchers should complete the following exercises independently, then have a volunteer share their example:**

How would I access Dan's mobile number?

```ruby
phone_numbers['Dan'][1]
```

How would I access Sam's home number?

```ruby
phone_numbers['Sam'][0]
```

How would I write a program that outputs each person's home and mobile number?

```ruby
phone_numbers.each do |name, numbers|
  puts "#{name}: #{numbers[0]} (home), #{numbers[1]} (mobile)"
end
```

How would I add a new entry in the phone book?

```ruby
phone_numbers['Adam'] = ['508.555.2134', '508.222.4324']
```

**Can anyone see any issues with this approach?**

* What if we add a work number? Where do we add it?
* How readable is this?  Is it easy to tell what piece of information I'm retrieving when I grab Sam's home phone number?

**What's an alternative solution?**

### Using a nested hash

```ruby
phone_numbers = {
  'Dan'   => {
    home: '508.555.5555',
    mobile: '508.555.6666'
  },
  'Jenny' => {
    home: '508.867.5309',
    mobile: '508.697.5555'
  },
  'Sam'   => {
    home: '508.777.7777',
    mobile: '508.946.3214'
  }
}
```

**Why is this better?**
* Easier to read and see what information we're retrieving.
* Our code won't change if the position of a piece of information changes.  In an array, if we insert a number at the beginning of the array, we have to change all of our code that referenced particular positions in the array.  Whereas in a hash, we can insert data to our heart's content without having to change our code.

#### Questions

**Same as above, for first data structure.**

How would I access Dan's mobile number?

```ruby
phone_numbers['Dan'][:mobile]
```

How would I access Sam's home number?

```ruby
phone_numbers['Sam'][:home]
```

How would I write a program that outputs each person's home and mobile number?

```ruby
phone_numbers.each do |name, numbers|
  puts "#{name}: #{numbers[:home]} (home), #{numbers[:mobile]} (mobile)"
end
```

How would I add a new entry in the phone book?

```ruby
phone_numbers['Adam'] = {
  home: '508.555.2134',
  mobile: '508.222.4324'
}
```

## Screencast

[Livecode of above link](. . . is here . . .)
