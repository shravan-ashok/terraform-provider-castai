## EKS and CAST AI example with CAST AI managed IAM policies

Following example shows how to onboard EKS cluster to CAST AI with CAST AI managed IAM policies.

IAM policies in the example are created by [castai/eks-iam-role/castai module](https://github.com/castai/terraform-castai-eks-role-iam).

Example configuration should be analysed in the following order:
1. Create VPC - `vpc.tf`
2. Create EKS cluster - `eks.tf`
3. Create IAM and other CAST AI related resources to connect EKS cluster to CAST AI - `castai.tf`

# Usage
1. Rename `tf.vars.example` to `tf.vars`
2. Update `tf.vars` file with your cluster name, cluster region and CAST AI API token
3. Initialize Terraform. Under example root folder run:
```
terraform init
```
4. Run Terraform apply:
```
terraform apply -var-file=tf.vars
```
5. To destroy resources created by this example:
```
terraform destroy -var-file=tf.vars
```

> **Note**
>
> If you are onboarding existing cluster to CAST AI you need to also update [aws-auth](https://docs.aws.amazon.com/eks/latest/userguide/add-user-role.html) configmap. In the configmap instance profile
> used by CAST AI has to be present. Example of entry can be found [here](https://github.com/castai/terraform-provider-castai/blob/157babd57b0977f499eb162e9bee27bee51d292a/examples/eks/eks_cluster_assumerole/eks.tf#L28-L38).
