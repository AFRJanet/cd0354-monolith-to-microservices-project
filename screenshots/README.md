# Screenshots
To help review your infrastructure, please include the following screenshots in this directory::

## Deployment Pipeline
* DockerHub showing containers that you have pushed
* GitHub repository’s settings showing your Travis webhook (can be found in Settings - Webhook)
* Travis CI showing a successful build and deploy job

## Kubernetes
* To verify Kubernetes pods are deployed properly
```bash
kubectl get pods
```
* To verify Kubernetes services are properly set up
```bash
kubectl describe services
```
* To verify that you have horizontal scaling set against CPU usage
```bash
kubectl describe hpa
```
* To verify that you have set up logging with a backend application
```bash
kubectl logs {pod_name}
```

## Project Submit Comment

frontend url is set to:
aec6871309d644e26bc531cecc786b35-164678345.us-east-1.elb.amazonaws.com

reverse-proxy url is:
ab098ad23a0e24cc599fa064e17deab3-647984639.us-east-1.elb.amazonaws.com

backend-user has defined replicas: 2 (screenshot api-user-replicas-2.png)
horizontal autoscaling was activated for backend-user --cpu=50 --min=1 --max=5 (screenshot kubectl_describe_hpa and kubectl_horizontal_autoscaling_hpa.png)

kubectl logs backend-user. Screenshot kubect_logs_user.png show successfully user fakeemail@email.com login.

.travis.yml has the configuration, that only when the main branch is changing,
that the build on Travis CI is triggered.

