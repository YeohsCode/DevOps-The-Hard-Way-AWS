# 翻译待定

**注意：此文件是原始英文内容的占位符，等待翻译成中文。以下是原始内容，仅供参考。**

---

# Connecting To Elastic Kubernetes Service (EKS)

When you're deploying locally, without any CI/CD to EKS, you'll need to authenticate from your local terminal.

Once you authenticate to EKS from your local terminal, a `kubeconfig` gets stored on your computer. The `kubeconfig` has all of the connection information and authentication needs to connect to EKS.

## Connecting To EKS

1. Run the following command to connect to EKS:
`aws eks --region *your_aws_region* update-kubeconfig --name *your_eks_cluster_name`

2. Once connected, you should be able to run commands like the following to confirm you're connected:
`kubectl get nodes`
