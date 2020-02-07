# Laravel Operation (Beginner for Web)

After installing Laravel, Bootstrap and Vue.js.

[Useful tutorial video](!https://laracasts.com/series/laravel-6-from-scratch)

Describe how to route the url to the html file, and use Controller to access database, and render the data which is received from database to View.

And some tests with Model.

## MVC

M \- Model

* In a todo app, Model might define what what a “task” is and that a “list” is a collection of tasks.
	 
V \- View

* View will define what the todos and lists looks like, visually. The tasks could have large font, or be a certain color.

C \- Controller

* Controller defines how a user adds a task, or marks another as complete. 

For example:

* The Controller connects the View’s add button to the Model, so that when you click “add task,” the Model adds a new task.

## Routes

Register the View for requesting url.

Define in 'routes/web'. (This document is focus on Web app)

For example:

```
Route::get('/', function () {
    return view('index');
});
```

When Apache receives GET which requests for '/' (it should be the web index), Laravel will return the View 'welcome' which is defined in 'resources/views'.

## View

Where you place the html file.

Define in 'resources/views'.

Here is an example

```
<!DOCTYPE html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        
        <!-- Prevent CSRF attack -->
        <meta name="csrf-token" content="{{ csrf_token() }}">
        
        <!-- Bootstrap CSS -->
        <link rel="stylesheet" href={{ mix('css/app.css')}}>

        <title>Hello, world!</title>
    </head>
    <body>
        <h1 class="text-center">Hello, world!</h1>
        
        <!-- Vue.js example -->
        <div id='app'>
            <example-component></example-component>
        </div>
        
        <!-- Webpack (vue.js, bootstrap.js, jquery.js, popper.js, app.js) -->
        <script src={{ mix('js/app.js') }}></script>
    </body>
</html>
```

# Create Database

> php artisan make:database
