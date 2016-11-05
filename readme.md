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
(Don't include the default fields: id, name, description, slug, active_flag, author_id, timestamps)
```
php artisan make:scaffold Object --ui=sui2 --schema="title:string:default('Object 1'), body:text"
```
Or with more options
```
php artisan make:scaffold Object \
	--schema="title:string:default('Object 1'), body:text" \
	--ui="sui2" \
	--prefix="settings"
```

`php artisan make:scaffold --ui=sui2 --schema="title:string" Object`
These commands will generate:

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

After migrating you should add the fields you added to the schema, to the controller as they are not added during the scaffold process. Ensure you add them to the create and update methods and include in validation if needed. The default fields will work out-the-box.

The stubs use the model name to add the icon also, in most cases this will not match up with a Semantic UI icon in which case you will need to choose one and then modify the scaffolds with the new icon name
[Semantic UI icons](http://semantic-ui.com/)

## Custom stub
Create a new folder inside **Stubs > views** with your UI name as the folder name

Custom fields in `Stubs > views > **ui-name** > fields`

Custom pages in `Stubs > views > **ui-name** > pages`
