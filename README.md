# How to Set Docker Environment ENV Variables?

The ENV instruction sets the environment variable <key> to the value <value>. The environment variables set using ENV will persist when a container is run from the resulting image.

- You can pass ENV variables not only during the image building but also at runtime when your containers are running
- ENV variables are usually your API keys, database URLs, secret keys, etc.
- Like ARG variables, the ENV can also have a default value in the dockerfile. 
- You can override ENV values set in a Dockerfile by providing updated ENV values through your docker-compose.yml file or Docker CLI.


server.js file env has been set *app.listen(process.env.PORT);* that are pass via cli --env-file project root directory.

**Steps 1:** Build docker image.

`docker build -t nasirnjs/nodejs:0.1 .`\

**Steps 2:** Run build image via ENV values
`docker run -p 8080:8000 -e PORT=8000 nasirnjs/nodejs:0.1`\
or
`docker run -p 8080:8000 --env-file .env nasirnjs/nodejs:0.1`

Now Browse `http://localhost:8080/`