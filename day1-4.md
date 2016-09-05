# PHPDoc for code completion in Eclipse

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
<?php
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
<?php
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
<?php
/** @var \DateTime $datetime */
$datetime->
```

Magic getter method

```
<?php
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
<?php
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
