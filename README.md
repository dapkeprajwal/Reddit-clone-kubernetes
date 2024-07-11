# Project: Reddit Clone Application

# Description 

As part of a software development project, I designed and implemented a robust continuous integration (CI) and continuous deployment (CD) pipeline for a Reddit clone application. The pipeline incorporated Docker, Docker Hub, and Kubernetes technologies to achieve a seamless, automated flow from code changes to deployment.

# Technologies Used: 

Docker, Docker Hub, Kubernetes, CI/CD, Containerization, Automation, Monitoring, Logging, Reddit Clone Application.

# Dockerfile 

Create a Dockerfile to build application 

docker biuld . -t dapkeprajwal/reddit-clone-app

Then push app folder to dockerhub with :

docker push dapkeprajwal/reddit-clone-app:latest

# Deployments
 create a kubernetes manifest file using yml to craete deployment
 
 In deployment use replica for load balancing 

 kubectl apply -f deployment.yml 

 then check the deployments using : kubectl get deployments

 result:

 ![Screenshot 2024-07-11 184910](https://github.com/dapkeprajwal/Reddit-clone-kubernetes/assets/113695938/c033a6e3-ca43-4080-ad70-933be4f2e85c)

 Check th pods that are runnig : kubectl get pods

 result:

 ![Screenshot 2024-07-11 184943](https://github.com/dapkeprajwal/Reddit-clone-kubernetes/assets/113695938/86b9ba12-9014-42f6-adcd-eb7148433417)

 # Service

 create service : kubectl apply -f service.yml

 check the service : kubectl get svc

 result:

 ![Screenshot 2024-07-11 185038](https://github.com/dapkeprajwal/Reddit-clone-kubernetes/assets/113695938/054eced3-d337-444c-8607-b5f83449dc2d)

 # Ingress

 create ingress : kubectl apply -f ingress.yml

 check the ingress : kubectl get ingress

 result:

 ![Screenshot 2024-07-11 185144](https://github.com/dapkeprajwal/Reddit-clone-kubernetes/assets/113695938/665133d5-4fb5-48f5-9736-eed0bf1e3444)

 # Expose Deployment

 Now expose deployment to a nodeport so it can run on browser

 kubectl expose deployment reddit-clone-deployment --type=NodePort

 Now change the port using port forwarding

 kubectl port-forward svc/reddit-clone-service 3000:3000 --address 0.0.0.0

 # Main Result 

 ![Screenshot 2024-07-11 170343](https://github.com/dapkeprajwal/Reddit-clone-kubernetes/assets/113695938/004260f0-ddad-4953-81c4-0b7e20d8c10f)


 

 



 



 

 
 








