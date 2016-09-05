# Introduction to PHPUnit 

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Create test file

```
// tests/HelloTest.php

<?php

class HelloTest extends \PHPUnit_Framework_TestCase
{
    public function testAssertTrue()
    {
        $this->assertTrue(false, 'False is not true');
    }

    public function testAssertEquals()
    {
        $expected = 'foo';
        $actual = 'bar';
        $this->assertEquals($expected, $actual, 'Expected is not equal actual');
    }

    public function testAssertSame()
    {
        $calc = 1 + 1;
        $this->assertSame('2', $calc, 'AssertSame is strict comparison');
    }
}
```

Run phpunit

```
$ phpunit tests/HelloTest.php
```

Verbose mode

```
$ phpunit tests/HelloTest.php --verbose
```

TestDox mode

```
$ phpunit tests/HelloTest.php --testdox
```

Code coverage

```
$ phpunit tests --coverage-text
$ phpunit tests --coverage-html phpunit-coverage.html
```

see [phpunit manual](https://phpunit.de/manual/current/en/code-coverage-analysis.html) for detail
