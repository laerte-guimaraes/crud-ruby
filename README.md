# TIPS

````rails
route to:
````
Define a roda default

## 

````rails
resources
````

Cria rotas default para o controller informado.

Ex:

````rails
resources :tasks
````

Cria as rotas:

|  Verbo HTTP |     Caminho     | Controller#Action |                       Uso                      |
|-------------|-----------------|-------------------|------------------------------------------------|
|     GET     | /tasks          |   tasks#index     | Página com todas as tarefas                    |
|     GET     | /tasks/new      |   tasks#new       | Página para o formulário de criação de tarefas |
|     POST    | /tasks          |   tasks#create    | Criar uma tarefa no banco                      |
|     GET     | /tasks/:id      |   tasks#show      | Mostra detalhes de uma tarefa                  |
|     GET     | /tasks/:id/edit |   tasks#edit      | Página para o formulário de edição de tarefas  |
|  PUT/PATCH  | /tasks/:id      |   tasks#update    | Edita uma tarefa no banco                      |
|    DELETE   | /tasks/:id      |   tasks#destroy   | Apaga uma tarefa no banco                      |