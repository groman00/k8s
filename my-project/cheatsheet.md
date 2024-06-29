docker build . --tag node-docker

kubectl apply -f app.yml

kubectl delete -f app.yml

docker run -p 8080:3000 node-docker

docker tag node-docker:latest gregorymichaelroman/sample-app:latest

docker push gregorymichaelroman/sample-app:latest
