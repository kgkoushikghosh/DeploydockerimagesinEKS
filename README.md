# DeploydockerimagesinEKS and run through AWS Fargate
This is a small sample project to deploy a dummy image from docker hub to EKS.
To do so we need to follow below steps
1 download and install AWS Cli and configure the same
2 download and isntall kubectl
3 download and install eksctl
3 create a cluster with "eksctl create cluster --name <cluster_name> --region <region> --fargate"
4 create a fargate profile through code in Create_fargateprofile file.
5 apply deployment.yaml
6 create IAM OIDC provider through "eksctl utils associate-iam-oidc-provider --cluster $cluster_name --approve"
7 create IAM policy with code in "Create_IAMPolcy.md" file.
8 create IAM service account with code in "Create_IAMServiceAccount.md".
9 Create the ALB controler with Helm with code in "deploy_ALB_Controler with Helm.md"
10 Finally run "kubectl get deployment -n kube-system aws-load-balancer-controller" command to check the ALB nodes are up and running or not.
11 If running then run "kubectl get ingress -n ngnix-app" and it will return the ALB adress copy that and run in browser and the Ngnix home page will be displayed.
