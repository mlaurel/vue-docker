# vue-docker
Vue, Express, Node, Mongo with Docker-compose setup for local in-house development. Based on the following tutorials:

https://medium.com/@anaida07/mevn-stack-application-part-1-3a27b61dcae0

https://medium.com/@audretschjames/venom-stack-docker-setup-for-local-development-457093761ad1

## Steps to Run

1. Clone this repository

> git clone https://github.com/mlaurel/vue-docker

2. Navigate into the directory vue-docker

> cd your-path-to/vue-docker

3. Build Docker Images

> docker-compose build

4. Run the stack :)

> docker-compose up

Your app should be running on (if using native docker): 

http://localhost:8080

Happy developing! 


## Configuration

There are 3 parts to this dockerized Vue app: Frontend (Vue), Backend (Node with Express), and Database (MongoDB).

The frontend is in the 'client' folder, backend in the 'server' folder, and the database is mounted to your current directory in the 'db' folder. 

NPM apps are a bit tricky to install in Docker, because the binaries have to be installed in the container. Though there are several solutions to this, I prefer the approach using the 'docker/entrypoint.sh' scripts that are in the 'client' and 'server' directories.


Be sure to change the environment variables (DATABASE_URL, API_URL) in docker-compose.yml according to your setup. Default should work if running on localhost.


## Warnings

Warning: If you run 'npm install' locally in the server or client folders, you'll need to delete 'node_modules' before running again with the docker setup. The binaries need to be install in the container's OS to work.


