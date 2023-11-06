---
layout: post
title: "Dummy data in laravel"
date: 2021-05-31 11:54:49 +0530
categories: laravel database
permalink: '/post/dummy-data-in-laravel'
---

Recently found out about using seeder to create fake data in laravel. Infact it can be used with factory 🧑‍🏭.

Dummy or fake data generation is an important part of testing database or visualizing data in browser. Laravel being a popular framework has a few ways to create dummy data. Now you can manually fill the database for testing but filling up data after every fresh migration is just too slow and you can do better than that. Let’s discuss two ways you might want to create dummy data.

- [Factory](https://laravel.com/docs/8.x/database-testing#defining-model-factories) -
  This is probably the more famous and used one. Factory uses [`faker`](https://fakerphp.github.io/formatters/) library to generate data. In order to create fake data we have to create a factory of the same model name. To create a factory for a `Post` model, we have to create a `PostFactory` by the command `php artisan make:factory PostFactory`. In `PostFactory.php` change `definition()` method as -
  ```
  public function definition()
  {
    return [
      'title' => $this->faker->sentence(),
      'body' => $this->faker->paragraph(),
    ];
  }
  ```
  The faker library will provide us with fake value of sentence and paragraph. In order create the fake data now we just have to open tinker with `php artisan tinker` and run in tinker console `Post::factory()->create()`.

- [Seeding](https://laravel.com/docs/8.x/seeding) -
  This is something I found recently. Creating dummy data by seeding is as easy as it gets. To create a seeder for `Post` model run `php artisan make:seeder PostSeeder`. In `PostSeeder` change `run` method as-
  ```
  public function run()
  {
    Post::create([
      'title' => 'lorem ipsum dolor imit',
      'body' => 'Similique molestias exercitationem officia aut. Itaque doloribus et rerum voluptate iure. Unde veniam magni dignissimos expedita eius.',
    ]);
  }
  ```
  In a seeder we provide value for all the required fields. And although it seems like just adding everything yourself, it has some nice advantages which you will see. Also if you already have a factory setup like we do, you can simply use the factory rather than adding all the field data.
  ```
  public function run()
  {
    Post::factory()->create();
  }
  ```
  Now add the `PostSeeder` to `database/seeders/DatabaseSeeder.php` `run` method `$this->call([PostSeeder::class])`. In order to store the data in database run `php artisan db:seed`. Your seed data is thus stored in database. To view it you can run `Post::get()` in `php artisan tinker` tinker console. After each fresh migration you can add `--seed` method to run seeder’s as well. `php artisan migrate:fresh --seed`. This along with the fact that seeder can be used hand to hand with factory is what makes it so great.