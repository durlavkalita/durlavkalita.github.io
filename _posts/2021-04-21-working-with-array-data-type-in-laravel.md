---
layout: post
title:  "Working with array data type in Laravel"
date:   2021-04-21 11:54:49 +0530
categories: laravel
permalink: '/post/working-with-array-data-type-in-laravel'
---

People love to work with array data types mostly due to it’s simplicity and ability store multiple data of same type in one variable. Let’s take a look at how array data type can be used to store data in a laravel application.

Laravel doesn’t have array as available column types. In order to store array data we have to make use of json column type and laravel casts functionality. Here is a step wise implementation of that.

- Step 0-
  Create a new laravel project.
  ```
    laravel new laradiy
    /* or */
    composer create-project laravel/laravel laradiy
  ```
  <br/>
- Step 1-
  Create `ArrayData` model.
  ```
    cd laradiy
    php artisan make:model ArrayData -mc
  ```
  -mc will create migrations and controller for us.
  <br/>
- Step 2-
  Edit migration table to accept array.
  `/database/migrations/2021_03_20_120154_create_array_data_table.php`
  ```
  public function up()
  {
    Schema::create('array_data', function (Blueprint $table) {
      $table->id();
      $table->json('random_list');
      $table->timestamps();
    });
  }
  ```
  It will create a json column of `random_list` , data will be stored as serialized JSON.
  <br/>
- Step 3-
  Modify the `ArrayData` model to accept `random_list` and cast it as array.
  `/app/Models/ArrayData.php`
  ```
  class Organisation extends Model
  {
    use HasFactory;
    protected $fillable= ['random_list'];
    protected $casts = [
    'random_list' => 'array'
    ];
  }
  ```
  The array cast will automatically deserialize `random_list` to a PHP array when you access it on your Eloquent model.
  <br/>
- Step 4-
  Now let’s modify the `ArrayDataController` to store and display the data stored.
  `/app/Http/Controllers/ArrayDataController.php`
  ```
  use App\Models\ArrayData;
  class ArrayDataController extends Controller
  {
    public function create()
    {
      ArrayData::create([
      'random_list' => [1,2,3],
      ]);
      return 'done';
    }
    public function index()
    {
      $data = ArrayData::find(1);
      dd($data->random_list);
    }
  }
  ```
  The `create` function will create and store `random_list` to your database. The index function will display `random_list` array.
  <br/>
- Step 5-
  Let’s create the routes to check our application.
  `/routes/web.php`
  ```
  use App\Http\Controllers\ArrayDataController;
  Route::get('/arraydata', [ArrayDataController::class, 'index']);
  Route::get('/createdata', [ArrayDataController::class, 'create']);
  ```
  <br/>
- Step 6-
  Now lets run the migrations
  ```
  php artisan migrate
  php artisan serve
  ```
  <br/>
  Open [localhost:8000](http://localhost:8000/) . Go to `/createarray` , it will create an entry in the database. Now go to `/arraydata` , and you will see your `random_list` array printed out.

  So, that’s how array data can be used in laravel. Hope this helps. See you later, alligator.
