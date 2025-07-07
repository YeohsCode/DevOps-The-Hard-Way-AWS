# 翻译待定

**注意：此文件是原始英文内容的占位符，等待翻译成中文。以下是原始内容，仅供参考。**

---

# Create The Kubernetes Manifest

At this point you have successfully created a Docker image from the Uber app and stored it in ECR.

Now it's time to set up the Kubernetes manifest, which will take the application and deploy it to EKS.

## The Manifest

The Kubernetes manifest will consist of two components:
- The deployment
- The service

The deployment is what gets the application running in Kubernetes

The service is what exposes the Kubernetes application so you can, for example, reach the frontend from a load balancer hostname or IP.

The manifest can be found in the `kubernetes_manifest` directory. Ensure on line `31` to change the image URL to the one you have in your AWS account.
