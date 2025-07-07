# 创建Uber应用的Docker镜像

本实验将指导您创建容器化Uber应用的Docker镜像

## 创建Docker镜像

1. 进入*Docker*目录（包含Dockerfile和app子目录）  
   `cd Docker`

2. 查看Dockerfile内容

3. Dockerfile关键配置说明：
   - 基础镜像：使用最新版Python官方镜像
   - 工作目录：创建`/build`目录作为应用目录
   - 文件复制：将app目录和requirements.txt复制到镜像中
   - 依赖安装：自动安装Python依赖
   - 启动命令：容器启动时自动运行应用

4. 构建Docker镜像命令：  
`docker build -t uberapp .`

参数说明：
- `-t uberapp`：指定镜像名称
- `.` ：表示Dockerfile位于当前目录

5. 验证镜像创建成功：  
`docker image ls`

## 本地运行Docker镜像

创建镜像后，可通过以下步骤测试运行：

1. 启动容器：  
`docker run -tid uberapp`

参数说明：
- `-t`：分配伪终端
- `-i`：保持STDIN打开
- `-d`：后台运行模式

2. 查看运行中的容器：  
`docker container ls`

成功运行后将在列表中看到该容器
