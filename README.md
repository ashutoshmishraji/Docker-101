# Docker-101


This tutorial has been written with the intent of helping folks get up and running
with containers and is designed to work with Docker Desktop. While not going too much 
into depth, it covers the following topics:

- Running your first container
- Building containers
- Learning what containers are running and removing them
- Using volumes to persist data
- Using bind mounts to support development


## Getting Started

If you wish to run the tutorial, you can use the following command after installing Docker Desktop:

```bash
docker run -d -p 3000:3000 ashutoshmishraji/todo-app
```

Once it has started, you can open your browser to [http://localhost](http://localhost).


 docker build -t todo-app .  

 docker run -dp 3000:3000 todo-app

 In the src/static/js/app.js file, update line 56 to use the new empty text.

 -                <p className="text-center">No items yet! Add one above!</p>
 +                <p className="text-center">You have no todo items yet! Add one above!</p>

 Let’s build our updated version of the image, using the same command we used before.

 docker build -t todo-app .

Let’s start a new container using the updated code.

 docker run -dp 3000:3000 getting-started

 docker login -u YOUR-USER-NAME

 docker tag todo-app YOUR-USER-NAME/todo-app

  docker push YOUR-USER-NAME/todo-app

    docker run -d ubuntu bash -c "shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null"

    docker exec <container-id> cat /data.txt

     docker run -it ubuntu ls /


     Persit DB
     By default, the todo app stores its data in a SQLite Database at /etc/todos/todo.db.

      docker volume create todo-db

      docker rm -f <id>

      docker run -dp 3000:3000 -v todo-db:/etc/todos todo-app

      docker volume inspect

      docker run -dp 3000:3000 \
     -w /app -v "$(pwd):/app" \
     node:12-alpine \
     sh -c "yarn install && yarn run dev"


-dp 3000:3000 - same as before. Run in detached (background) mode and create a port mapping
-w /app - sets the “working directory” or the current directory that the command will run from
-v "$(pwd):/app" - bind mount the current directory from the host in the container into the /app directory
node:12-alpine - the image to use. Note that this is the base image for our app from the Dockerfile
sh -c "yarn install && yarn run dev" - the command. We’re starting a shell using sh (alpine doesn’t have bash) and running yarn install to install all dependencies 
and then running yarn run dev. If we look in the package.json, we’ll see that the dev script is starting nodemon.

## Contributing

If you find typos or other issues with the tutorial, feel free to create a PR and suggest fixes!

If you have ideas on how to make the tutorial better or new content, please open an issue first before working on your idea. While we love input, we want to keep the tutorial  scoped to newcomers.
As such, we may reject ideas for more advanced requests and don't want you to lose any work you might
have done. So, ask first and we'll gladly hear your thoughts!
