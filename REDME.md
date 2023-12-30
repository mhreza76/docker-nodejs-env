server.js file env has been set *app.listen(process.env.PORT);* that are pass via cli --env-file project root directory.


`docker build -t nasirnjs/nodejs:0.1 .`\
`docker run -p 8080:8000 -e PORT=8000 nasirnjs/nodejs:0.1`\
`docker run -p 8080:8000 --env-file .env nasirnjs/nodejs:0.1`


Now Browse

http://localhost:8080/