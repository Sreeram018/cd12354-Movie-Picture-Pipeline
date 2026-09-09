Public GitHub Repository:
https://github.com/Sreeram018/cd12354-Movie-Picture-Pipeline

Note: AWS resources (EKS cluster, LoadBalancers) were verified live and 
then torn down after capturing evidence, to conserve AWS sandbox credits.

Both CD workflows (frontend-cd.yaml and backend-cd.yaml) now include 
automated deployment verification steps, added per reviewer feedback:
- kubectl rollout status
- kubectl get all
- kubectl describe deploy
- aws ecr describe-images

These run automatically as part of every deployment and are visible in 
the GitHub Actions logs for full auditability.

Evidence Included:
- Frontend CI successful (frontend-ci-success.png)
- Backend CI successful (backend-ci-success.png)
- Frontend application live in browser, URL bar visible (frontend-url-proof.png)
- Backend /movies API live in browser, URL bar visible (backend-url-proof.png)
- Cluster state - pods, services, deployments (kubectl-get-all.png)
- Frontend deployment details with matching image tag (kubectl-describe-deploy-frontend.png)
- Backend deployment details with matching image tag (kubectl-describe-deploy-backend.png)
- Frontend Docker image in ECR (ecr-frontend-image.png)
- Backend Docker image in ECR (ecr-backend-image.png)
- Backend CD pipeline verification steps, in-workflow (backend-cd-verification-1.png, -2.png, -3.png)
- Frontend CD pipeline verification steps, in-workflow (frontend-cd-verification-1.png, -2.png, -3.png)
