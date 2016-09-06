# Run Fizz buzz on Terminal

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Create Command

```
$ php artisan make:console FizzbuzzCommand --command=app.fizzbuzz
```

Add FizzbuzzCommand to app/Console/Kernel.php

```
// app/Console/Kernel.php

    protected $commands = [
        ... 
        Commands\FizzbuzzCommand::class,
    ];
```

Make sure FizzbuzzCommand is registered

```
$ php artisan | grep app.fizzbuzz

  app.fizzbuzz         Command description
```

Call FizzbuzzService in FizzbuzzCommand.php

```
// app/Console/Commands/FizzbuzzCommand.php

    public function handle()
    {
        $fb = new FizzbuzzService();
        for ($i = 1; $i =< 50; $i ++) {
            $this->output->write($fb->handle($i) . ', ');
        }
    }
```

Run command

```
$ php artisan app.fizzbuzz

1 ,2, Fizz, 4, Buzz
```
