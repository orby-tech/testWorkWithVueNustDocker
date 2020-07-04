#Test work with VueJS, NustJS, VuestifyJS, Docker 

# Start with Docker
cd ./testapp
docker build -t vuejs-cookbook/dockerize-vuejs-app .
docker run -it -p 8080:8080 --rm --name dockerize-vuejs-app-1 vuejs-cookbook/dockerize-vuejs-app


#Start in dev mode

cd testapp
npm run dev
