Create create project with project name :-
oldway :-
npm install -g create-react-app
create-react-app client
new way :- (solve old depnedencies issue)
npx create-react-app client

Inside FrontEnd:-
npm run test
npm run build (with create a build folder)
npm run start (to start the webserver)

To make docker simulate as development :- [npm run start]
1. create Dockerfile.dev
2. To build run <docker build -f Dockerfile.dev .>'
3a <docker run -p 3000:3000 <id> -v pwd:/app> (for window set the volumns for harddisk to refer local path instead)
3b <docker run -p 3000:3000 <id> -v $(pwd):/app> (for unix set the volumns for harddisk to refer local path instead)
3b <docker run -p 3000:3000 <id> -v ${pwd}:/app> (for for 10 pro set the volumns for harddisk to refer local path instead)
3c <docker run -p 3000:3000 <id> -v /app/node_modules -v $(pwd):/app> (-v /app/node_modules. Put a bookmark on the nodes folder)

put command to docker-compose.yml and run docker-compose up

2 ways Test on development environment:- [npm run test]
A) 1st window <docker-compose up>
A) 2nd window and attach test scripts <docker exec -it <container id> npm run test
B) or Build npm run test in docker-compose.yml

Production deployment :- [npm run build]
Need nGinx & node (multle-step docker builds approach)

Test locally :-

docker build .
docker run -p 8080:80 <id>

CICD setup with github and travis CI :-
1. Create github new repo docker-react (https://github.com/datolim/docker-react.git). 
   Init local master repo and push over github
   
   cd frontend 
   git init
   git add .
   git commit -m "init commit"
   git remote add origin https://github.com/datolim/docker-react.git
   git push origin master