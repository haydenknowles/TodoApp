# Todo App

Simple Todo app written in Angular/Typescript, with a .NET core API backend

## Demo

Demo running in ECS Fargate can be found at http://haydenk.tk, and the corresponding [API](http://api.haydenk.tk/api/todoitems).

## Building

Clone the repo:

`git clone --recurse-submodules https://github.com/haydenknowles/TodoApp.git`

Modify the appUrl in `todo-angular/src/environments/environment.ts` to be the IP/domain name of the host docker machine.

Build the docker images:

```sh
docker build -t netapi TodoAngularAPI/TodoAngular
docker build -t ngtodo todo-angular
```

## Running

Create and run a docker container from the images built:
```sh
docker run -d -p 8888:80  --name todo-backend netapi
docker run -d -p 4200:4200 --name todo-frontend todoapp
```