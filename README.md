# TIPS

## ROUTING
````rails
root to: '@controller#@view'
````
Define a default view path for this app

Ex:
````rails
root to: 'home#welcome'
````

## 

````rails
resources
````

Create default routes for selected **controller**.

Ex:

````rails
resources :tasks
````

Will create this routes:

|     Verb    |       Path      | Controller#Action |                       Use                      |
|-------------|-----------------|-------------------|------------------------------------------------|
|     GET     | /tasks          |   tasks#index     | Page with all tasks                            |
|     GET     | /tasks/new      |   tasks#new       | Page with form to create tasks                 |
|     POST    | /tasks          |   tasks#create    | Create one task on database                    |
|     GET     | /tasks/:id      |   tasks#show      | Show of a specific task                        |
|     GET     | /tasks/:id/edit |   tasks#edit      | Page with form to update an specific tasks     |
|  PUT/PATCH  | /tasks/:id      |   tasks#update    | Update one specific task on database           |
|    DELETE   | /tasks/:id      |   tasks#destroy   | Delete one specific task on database           |

## 

## REFERENCING AND CARDINALITY
To reference tables (add a foreign key for example), its necessary execute one migration using:
````rails
rails generate migration add_@model1_to_@model2 @model2:references
````

Ex:
````rails
rails generate migration add_category_to_task category:references
````

Will be receive the attribute **category_id** for **Task** model's, and attribute **task_id** for **Category** model's.

## 

On relactions **1:1** must be added on _Model_:
````rails
belongs_to :@model
````

Ex (1 **Task** has 1 **Category**):
````rails
belongs_to :category
````

On relactions **1:n** must be added on _Model_:
````rails
has_many :@model
````

Ex (1 **Category** has 1 or + **Task's**): 
````rails
has_many :tasks
````
