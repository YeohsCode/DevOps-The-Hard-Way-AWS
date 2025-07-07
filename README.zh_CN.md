# DevOps硬核实践-AWS

本教程提供完整的实战解决方案，指导您使用DevOps技术和实践部署应用到AWS云服务和基础设施。

该仓库包含免费的实验指南、文档、架构图等资源，从实战角度展示如何在AWS中建立完整的工作流和DevOps环境。

## DevOps场景
假设您在一家传统架构为主的企业工作：存在大量裸金属服务器、虚拟化环境、人工部署应用以及基于传统IT知识的**老旧**实践。

您被引入公司和团队进行现代化改造，使组织不仅能成功转型，还能保持竞争优势。管理层已认识到保持竞争力所需的技术复杂度，深知必须进行变革，否则企业将面临淘汰...

## DevOps解决方案
解决方案是部署Uber注册页面API。当前该方案运行在裸金属服务器上，现在需要注入DevOps实践进行改造。

![](images/uber.png)

作为DevOps工程师，您主要职责是部署而非开发应用（本教程不涉及应用开发）。

*完整声明* - 我已对Uber原始应用进行修改以兼容Python3，仓库地址：
https://github.com/AdminTurnedDevOps/Python-Sample-Application

## 技术架构
您将使用以下技术和平台构建DevOps环境：

1. AWS
    - 用于托管应用、云基础设施及其他保障Uber应用部署所需服务
2. GitHub
    - 存储应用代码和基础设施/自动化脚本
3. Python
    - Uber应用开发语言，也用于Terraform之外的自动化任务
4. Terraform
   - 创建存储Terraform状态文件的S3存储桶
   - 创建AWS ECR容器仓库
   - 创建EKS集群
5. Docker
   - 构建Docker镜像
   - 将镜像存储到AWS ECR
6. Kubernetes
   - 运行容器化的Uber应用（本教程使用EKS进行容器编排）
7. CI/CD
   - 使用GitHub Actions创建EKS集群
8. 自动化测试
    - 使用Checkov进行Terraform代码策略、安全和静态分析
9. 监控与可观测性
    - EKS集群和容器化应用的日志、追踪、指标监控

## 实验列表
1. [先决条件](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/prerequisites.md)
2. AWS:
    - [配置编程访问AWS凭证](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/AWS/1-Configure-Credentials-To-Access-AWS.md)
3. Terraform - 创建运行Uber应用所需的所有AWS云服务/基础设施
    - [创建存储TFSTATE文件的S3存储桶](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/terraform-state-s3-bucket/Create-S3-Bucket-To-Store-TFSTATE-Files.md)
    - [创建弹性容器仓库(ECR)](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/Terraform-AWS-Services-Creation/2-Create-ECR.md)
    - [创建EKS集群和VPC](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/eks-vpc-terraform-module/Module-creation.md)
5. Docker - 容器化本地Uber应用并存储到AWS ECR
    - [创建Docker镜像](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/Docker/1-Create-Docker-Image.md)
    - [登录AWS ECR仓库](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/Docker/Push%20Image%20To%20ECR.md)
6. Kubernetes - 连接EKS并编写Kubernetes部署清单
    - [从终端连接EKS](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/kubernetes_manifest/1-Connect-To-EKS.md)
    - [创建Kubernetes清单](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/kubernetes_manifest/2-Create-Kubernetes-Manifest.md)
7. 自动化测试 - 确保Terraform代码符合策略、安全和静态分析要求
    - [安装并运行Checkov](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/Terraform-Static-Code-Analysis/1-Checkov-For-Terraform.md)
8. CI/CD - 使用GitHub Actions自动创建EKS集群
    - [创建GitHub Actions CI/CD流水线](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/Terraform-AWS-Services-Creation/4-Run-CICD-For-EKS-Cluster.md)
9. 监控与可观测性
    - [使用Datadog和Helm配置监控](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/blob/main/monitoring-and-observability/monob.md)
10. 性能与资源优化（进行中）
