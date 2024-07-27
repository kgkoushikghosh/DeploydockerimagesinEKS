eksctl create fargateprofile \
    --cluster demo-cluster-ngnix \
    --region us-east-1 \
    --name alb-ngnix-app \
    --namespace ngnix-app
