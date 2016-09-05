# Fizz buzz with Test Driven Development

What is Fizz buzz

> Fizz buzz is a group word game for children to teach them about division. Players take turns to count incrementally, replacing any number divisible by three with the word "fizz", and any number divisible by five with the word "buzz".
> 
> Quotations: [Wikipedia: Fizz buzz](https://en.wikipedia.org/wiki/Fizz_buzz)

- Iterate number one to fifty
- A number divisible by three, Print "Fizz"
- A number divisible by five, Print "Buzz"
- A number divisible by three and five, Print "Fizz Buzz"

Example

```
1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, Fizz Buzz, 16, 17, Fizz, 19, Buzz, Fizz, 22, 23, Fizz, Buzz, 26, Fizz, 28, 29, Fizz Buzz, 31, 32, Fizz, 34, Buzz, Fizz, ...
```

# Test driven development cycle

1. Add a test
1. Run all tests and see if the new test fails
1. Write the code
1. Run tests
1. Refactor code
1. Repeat

> Quotations: [Wikipedia: Test-driven development](https://en.wikipedia.org/wiki/Test-driven_development#Test-driven_development_cycle)

# Play Fizzbuzz

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Create test file

```
// tests/Service/FizzbuzzServiceTest.php

<?php

namespace Test\Service;

class FizzbuzzServiceTest extends \PHPUnit_Framework_TestCase
{
    public function testGetFizz()
    {
        // Your code.
    }
}

class FizzbuzzService
{
    // Your code.
}
```

Run test

```
$ phpunit tests/Service/FizzbuzzServiceTest.php
```

Don't search the Internet for Fizz buzz example.
