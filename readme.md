# Laravel 5.2 Scaffold Generator

Hi, this is a forked scaffold generator for Laravel 5.2. using Semantic UI styles instead of Bootstrap

## Usage

### Step 1: Install Through Composer

```
composer require 'robbielove/l5scaffold' --dev
```
install landish/pagination in your project - this project uses it for pagination Controllers
```
composer require landish/pagination
```

### Step 2: Add the Service Provider

Open `config/app.php` and, to your **providers** array at the bottom, add:

```
"Robbielove\L5scaffold\GeneratorsServiceProvider"
```

### Step 3: Run Artisan!

You're all set. Run `php artisan` from the console, and you'll see the new commands `make:scaffold`.

## Examples


```
php artisan make:scaffold Object --schema="title:string:default('Object 1'), body:text"
```
This command will generate:

```
app/Object.php
app/Http/Controllers/ObjectController.php
database/migrations/2015_04_23_234422_create_objects_table.php
database/seeds/ObjectTableSeeder.php
resources/views/layout.blade.php
resources/views/objects/index.blade.php
resources/views/objects/show.blade.php
resources/views/objects/edit.blade.php
resources/views/objects/create.blade.php
```
The generated migration will include by default:

```
$table->increments('id');
$table->string('name')->default('Un-Named {{Class}}');
$table->string('slug');
$table->text('description');
[Your custom fields]
$table->boolean('active_flag');
$table->integer('author_id')->unsigned()->default(0);
$table->foreign('author_id')->references('id')->on('users');
$table->timestamps();
```

Don't forget to run:

```
php artisan migrate
```
