# eks-demo - Node.Js
 
1. Set up a new IAM role with EKS permissions
create ECR repo, build push your docker image there.

2.Create VPC for our cluster, that can be created manually if we want. But I'm using AWS Cloudformation because AWS already has a template for creating a public and private subnet VPC. templete link have provided below.

https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-01-09/amazon-eks-vpc-sample.yaml

3. once you create VPC note down security group, subnets & VPC ID, now create EKS cluster using aws CLI as mentioned below

now modify VPC, subnet..etc,, in cluster.yml  available in repo

now execute below command to create our cluster on EKS

eksctl create cluster -f cluster.yaml --kubeconfig=C:\Users\{user}\.kube\config

4.once custer is in active state update your kube config with the EKS cluster name that you created.


5. Now deploy deployment.yaml using below command 

kubectl apply -f deployment.yaml

6. Now apply service.yml in code. & now open the port & try to access that with the node IP 

