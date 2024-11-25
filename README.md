# eXpense
A microservice App to monitor and manage Expenses of employees, Developed with Python Flask, Docker, Kubernetes, On security JWT and for messaging services RabbitMQ



===================================================================================================================
# Build images
docker build -t your-dockerhub-username/authentication-services ./authentication-services
docker build -t your-dockerhub-username/employee-services ./employee-services
docker build -t your-dockerhub-username/finance-services ./finance-services

# Push to Docker Hub
docker push your-dockerhub-username/authentication-services
docker push your-dockerhub-username/employee-services
docker push your-dockerhub-username/finance-services


===================================================================================================================
# Create namespace
kubectl apply -f k8s/namespace.yaml

# Deploy Authentication Gateway
kubectl apply -f authenticationservices/k8s/deployment.yaml
kubectl apply -f authenticationservices/k8s/service.yaml

# Deploy Employee Services
kubectl apply -f employee-services/k8s/deployment.yaml
kubectl apply -f employee-services/k8s/service.yaml

# Deploy Finance Services
kubectl apply -f finance-services/k8s/deployment.yaml
kubectl apply -f finance-services/k8s/service.yaml


