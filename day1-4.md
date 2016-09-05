# PHPDoc for code completion in Eclipse

Create file to ~/Code/Laravel/public/code_completation.php in Eclipse

Method arguments

```
<?php
class Baz1
{
    /**
     * @param \DateTime $datetime Description
     */
    public function foo($datetime)
    {
        $datetime->
    }
}
```

Returned value

```
class Baz2
{
    /**
     * @return \DateTime Description
     */
    public function foo()
    {
        return new \DateTime();
    }
}

$baz2 = new Baz2();
$datetime = $baz2->foo();
$datetime->
```

An array with the method arguments

```
class Baz3
{
    /**
     * @param \DateTime[] $datetimes Description
     */
    public function foo($datetimes)
    {
        foreach ($datetimes as $datetime) {
            $datetime->
        }
    }
}
```

Variables

```
/** @var \DateTime $datetime */
$datetime->
```

Magic getter method

```
/**
 * @method \DateTime datetime() Description
 */
class Baz5
{
    private $container;

    public function __get($name)
    {
        return $this->container[$name];
    }
}

$baz5 = new Baz5();
$datetime = $baz5->
```

Magic property

```
/**
 * @property integer $id
 * @property string $title
 * @property string $body
 */
class Baz6
{
}

$baz6 = new Baz6();
$baz6->
```
