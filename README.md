An application which shows the voting percentage and build using docker and kuberenetes.

<kbd>
<img width="1468" alt="Screenshot 2024-03-16 at 1 15 27 PM" src="https://github.com/SidhantMathur20/Voting-Application/assets/88873670/e182f917-4d73-494e-8207-1e69d9bd6928">
</kbd>

Architecture:-
<kbd>
<img width="1442" alt="Screenshot 2024-03-16 at 1 18 22 PM" src="https://github.com/SidhantMathur20/Voting-Application/assets/88873670/111fffb9-b8cd-476d-9598-3ff914406fb7">
</kbd>

Commands used for running the application!
1.  kubectl create -f voting-app-deploy.yaml
2.  kubectl create -f voting-app-service.yaml
3.  kubectl create -f redis-deploy.yaml
4.  kubectl create -f redis-service.yaml
5.  kubectl create -f postgres-deploy.yaml
6.  kubectl create -f postgres-service.yaml
7.  kubectl create -f worker-app-deploy.yaml
8.  kubectl create -f result-app-deploy.yaml
9.  kubectl create -f result-app-service.yaml -> Above commands are used for creating deployments!
10.  kubectl get pods,svc,deployment -> Used list all the Pods, Services and Deployments!
11.  minikube service voting-service --url -> Provide a dummy url to access the following service!
12.  minikube service result-service --url -> Provide a dummy url to access the following service!
13.  kubectl scale deployment voting-app-deploy --replicas=3 -> To scale up the number of replicas to 3!
14.  kubectl get pods,svc,deployment
