# Laravel

## What is Laravel?

Laravel is an **open-source PHP framework** that is **easy to use, understand, and develop**.  
It follows the **MVC (Model-View-Controller) architecture** for better code organization and scalability.

---

## History of Laravel

- **2011** – Laravel was created by **Taylor Otwell**.
- **2012** – Released as **open-source**.
- **2013** – Laravel **4** was released.
- **2014** – Laravel **5** was released.
- **2015** – Laravel **5.1** was released.
- **2016** – Laravel **5.2 - 5.11** was released.

## MVC

Laravel is built upon the **MVC (Model-View-Controller) pattern**, separating the application logic (**Model**), presentation (**View**), and user interaction (**Controller**).

---

## Dependency Injection

**Dependency Injection** is a design pattern that allows a class to receive its dependencies from an external source rather than creating them itself.

---

## Routing

**Routing** is the process of determining how an application responds to a client request to a particular **endpoint** (a URI or path) and a specific HTTP request method (**GET, POST, etc.**).

---

## Eloquent ORM (Object-Relational Mapping)

**Eloquent ORM** simplifies database interaction by providing an **Active Record** implementation for working with databases.  
It provides a **fluent and expressive API** for querying and manipulating data.

# Why Use Laravel?

## Simplified Development

Laravel offers an **intuitive syntax** and **powerful features**, making development easier and more efficient.

---

## Rapid Prototyping

Laravel allows developers to **rapidly build and test applications** using scaffolding and **pre-configured components**.

---

## Security

Laravel provides **robust security features**, including:

- **Automatic escaping** to prevent cross-site scripting (XSS).
- **SQL injection protection** to secure database queries.

---

## Scalability

Laravel is designed to handle **large-scale applications** and can scale both **vertically** and **horizontally**, making it suitable for **growing businesses and high-traffic applications**.

# MVC Lifecycle in Laravel

## Flow of Execution

### **1. Request**

A **user request** is made to the server.

### **2. Route**

The request is **routed** to the appropriate **controller method** based on the defined routes.

### **3. Controller**

The **controller method** is executed, which may involve interacting with the **model** to fetch or process data.

### **4. Model**

The **model** interacts with the **database** to retrieve, update, or manipulate data.

### **5. View**

The **view** is rendered, passing data from the **controller** to display the desired output.

### **6. Response**

The final **response** is sent back to the user.

# Template Engine: Blade Templating

## Blade Templating

Laravel uses the **Blade template engine**, a **lightweight** and **powerful** templating language designed to create **hierarchical blocks and layouts** with predefined structures that include **dynamic content**.

### **Key Features of Blade:**

- **Template Inheritance** – Create master layouts and extend them in child views.
- **Dynamic Content** – Embed PHP code within Blade templates using `{{ }}` syntax.
- **Control Structures** – Use loops (`@foreach`, `@for`) and conditionals (`@if`, `@else`).
- **Components & Includes** – Reuse sections across multiple views.
- **Security** – Automatically escapes output to prevent XSS attacks.

# Essential Components and Features of Laravel

## 1. Blade Template Engine

Provides a **clean** and **efficient** way to create **dynamic views** with reusable components and layouts.

## 2. ORM (Eloquent)

Simplifies **database interaction** by providing a **fluent interface** for querying and maintaining data.

## 3. Routing

Offers a **flexible approach** for defining routes in a web application.

- Helps in **scaling** the application efficiently.
- Improves **performance** by optimizing request handling.

## 4. Authentication and Authorization

Built-in **authentication** and **authorization** system to **secure** the application effortlessly.

## 5. Artisan Console

A **command-line tool** that helps developers perform various tasks, such as:

- Running database migrations
- Generating boilerplate code
- Managing queues and scheduled tasks

# Composer

## What is Composer?

Composer is a **dependency management tool** for PHP. It allows you to **declare the libraries** your project depends on, and it will **manage (install/update) them** for you.

## Key Features of Composer:

- **Manages Dependencies** – Automatically installs and updates required PHP libraries.
- **Framework Support** – Helps create projects with a **maintained framework** like Laravel.
- **Third-Party Libraries** – Easily install and integrate **third-party packages**.
- **Version Control** – Ensures compatibility by managing package versions.

## Usage:

- Install dependencies with:
  ```sh
  composer install
  ```

````

# Installing a New Laravel Project

## Using Composer
To create a new Laravel project, run the following command:

```sh
composer create-project laravel/laravel project-name

````

# Laravel Artisan Commands

## Show All Artisan Commands

```sh
php artisan list
```

## Create a Controller in Laravel

```sh
php artisan make:controller ControllerName
```

## Create a Model in Laravel

```sh
php artisan make:model ModelName
```

## Clear Cache in Laravel

```sh
php artisan cache:clear
```

## Clear Routes Cache in Laravel

```sh
php artisan route:clear
```

## Clear Config Cache in Laravel

```sh
php artisan config:clear
```

## Optimize Application (Clears Routes, Configs & Resources)

```sh
php artisan optimize
```

# Laravel Aggregate Functions

In Laravel, aggregate functions are used to perform calculations on a set of values and return a single value.

## Some Basic Functions:

- **count()** – Returns the number of rows in a specified table.
- **max()** – Returns the largest value of a specified column.
- **min()** – Returns the smallest value of a specified column.
- **avg()** – Returns the average value of a specified column.
- **sum()** – Returns the sum of all values in a specified column.

---

## `name()` Method in Laravel

The `name()` method is used to assign a name to a route.

```php
Route::get('urlName', [ControllerName::class, 'methodName'])->name('routeName');
```

---

## Helper in Laravel

Helper in Laravel is a globally available function that simplifies common tasks, such as string manipulation and reusable functions.

### Laravel provides built-in functions like:

- `url()`
- `route()`
- `asset()`
- `config()`
- `env()`
- `csrf_token()`
- `session()`
- `old()`
- `trans()`

### Custom Helper in Laravel:

1. Create a folder in the `app` directory: `app/Helpers`
2. Create a file `Helpers.php`
3. Autoload it in the `composer.json` file

---

## Session in Laravel

A session in Laravel is a way to store user data across multiple requests. It allows data to persist between pages without using cookies or a database for every request.

### How Session Works:

1. Laravel assigns a unique ID to each session.
2. Data (e.g., authentication status, messages) is stored temporarily.

### Storing Data in Session:

```php
session()->put('sessionName', 'sessionValue');
session()->put('key', 'value');
session()->put('key', ['value1', 'value2']);
```

### Get Session Data:

```php
session('sessionName');
session()->get('sessionName');
```

### Remove Session Data:

```php
session()->forget('sessionName'); // Remove single session
session()->flush(); // Remove all sessions
```

---

## Laravel Maintenance Mode

Maintenance mode is used only during development or maintenance time.

### Enable Maintenance Mode:

```sh
php artisan down
```

### Disable Maintenance Mode:

```sh
php artisan up
```

---

## How to Create a Custom 404 Page in Laravel

Create a custom 404 error page by adding the following file:

```
resource/views/errors/404.blade.php
```

---

## Middleware in Laravel

Middleware acts as a filter for HTTP or HTTPS requests before they reach your application logic.
