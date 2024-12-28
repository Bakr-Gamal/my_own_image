# my_own_image

# Dockerfile
-------------
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
--------------------------
# package.json
--------------
{
  "name": "my-simple-project",
  "version": "1.0.0",
  "description": "A simple Node.js project",
  "main": "src/my-app.js", 
  "scripts": {
    "start": "node src/my-app.js" 
  },
  "dependencies": {} 
}
-------------------------------
sudo apt-get update
sudo apt-get install nodejs npm
sudo npm install
----------------------------------
docker login
----------------------------------
docker build -t 3715906/my-nodejs-app:latest .
----------------------------------
docker run -it -p 3000:3000 3715906/my-nodejs-app:latest

> my-simple-project@1.0.0 start
> node src/my-app.js

Hello from my Node.js app!


----------------------------------
bakr@bakr-virtual-machine:~/myproject/nodeJs$ docker push 3715906/my-nodejs-app:latest
The push refers to repository [docker.io/3715906/my-nodejs-app]
f03a2f85e5db: Pushed 
bb566fce6db6: Pushed 
12acc92d50ba: Pushed 
0fd7845186b5: Pushed 
0e35c2222d0a: Mounted from library/node 
cb0e765bc939: Mounted from library/node 
dbf4e3ba24d5: Mounted from library/node 
3e01818d79cd: Mounted from library/node 
latest: digest: sha256:23ed6bb451608504ba9c87625dc66978fccc12c170c061d45714d47b89e62119 size: 1985
bakr@bakr-virtual-machine:~/myproject/nodeJs$ 
