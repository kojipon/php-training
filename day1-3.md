# Database Seeder

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

create Seeder

```
$ php artisan make:seeder UsersSeeder
```

Edit Seeder
[Faker](https://github.com/fzaninotto/Faker)

```
// database/seeds/UsersSeeder.php

use App\User;

/**
 * Run the database seeds.
 *
 * @return void
 */
public function run()
{
    //delete all data.
    User::truncate();

    //faker
    $faker = Faker\Factory::create('en_US');

    //insert
    for ($i = 0; $i < 25; $i++) {
        $user = User::create();

        $user->name = $faker->userName();
        $user->email = $faker->unique()->email();
        $user->password = Hash::make($user->email);

        $user->save();

    }
}
```

Edit DatabaseSeeder

```
// database/seeds/DatabaseSeeder.php

/**
 * Run the database seeds.
 *
 * @return void
 */
public function run()
{
    Model::unguard();

    $this->call(UsersSeeder::class);

    Model::reguard();
}
```

Seed data

```
$ php artisan db:seed
```
