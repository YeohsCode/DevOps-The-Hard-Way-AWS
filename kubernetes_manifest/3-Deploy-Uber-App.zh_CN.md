# 翻译待定

**注意：此文件是原始英文内容的占位符，等待翻译成中文。以下是原始内容，仅供参考。**

---

# Deploy The Uber App

Once the EKS cluster is built and the Kubernetes manifest is ready, you're now ready to deploy the Kubernetes manifest.

1. `cd` into the `kubernetes_manifest` directory
2. Run the following command:
`kubectl create -f deployment.yml`

You'll see an output that specifies the service and deployment was created.

3. Run the following command to confirm that the deployment was successful:
`kubectl get deployments`
