docker build . --tag node-docker

kubectl apply -f app.yml

kubectl apply -f ./k8s/ --recursive

kubectl delete -f app.yml

docker run -p 8080:3000 node-docker

docker tag node-docker:latest gregorymichaelroman/sample-app:latest

docker push gregorymichaelroman/sample-app:latest

<!-- Dashboard -->

helm upgrade --install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace --namespace kubernetes-dashboard

kubectl -n kubernetes-dashboard port-forward svc/kubernetes-dashboard-kong-proxy 8443:443

greg$ kubectl apply -f k8s-dashboard/

kubectl -n kubernetes-dashboard create token admin-user
