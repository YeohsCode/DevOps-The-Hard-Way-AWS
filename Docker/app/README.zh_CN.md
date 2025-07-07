开发者版Uber应用示例

[![TravisCI](https://travis-ci.org/uber/Python-Sample-Application.svg?branch=master)](https://travis-ci.org/uber/Python-Sample-Application)
[![Coverage Status](https://coveralls.io/repos/uber/Python-Sample-Application/badge.png)](https://coveralls.io/r/uber/Python-Sample-Application)

https://developer.uber.com/

项目说明
-------------

这是一个基于Python/Flask的简易应用，提供Uber外部API的使用示例。这些API端点设计简洁、文档完善，旨在为开发者构建其他应用提供基础参考。


使用指南
---------------

1. 访问 https://developer.uber.com/ 注册Uber开发者账号
2. 创建新Uber应用，设置重定向URI为 `http://localhost:7000/submit` - 确保勾选 `profile` 和 `history` OAuth权限
3. 在根目录的 `config.json` 文件中填写相关信息，并设置环境变量：
   `UBER_CLIENT_ID` 和 `UBER_CLIENT_SECRET`
4. 执行命令：
   `export UBER_CLIENT_ID="`*{您的客户端ID}*`"&&export UBER_CLIENT_SECRET="`*{您的客户端密钥}*`"`
5. 安装依赖：`pip install -r requirements.txt`
6. 启动应用：`python app.py`
7. 浏览器访问 http://localhost:7000


测试流程
-------

1. 安装测试依赖：`make bootstrap`
2. 运行测试：`make test`
3. 如需重新生成测试夹具(fixtures)：
   - 运行应用获取主页面中的auth_token
   - 替换 `test_endpoints.py` 文件顶部的 `test_auth_token`
   - 重新运行测试


开发贡献
-----------

欢迎通过GitHub提交issue和PR参与开发！

1. 提交issue时请完整描述问题或功能需求
2. 提交PR时请确保添加相应测试，并通过 `make test` 运行完整测试套件

部署到Heroku
----------------

点击下方按钮在Heroku部署此应用：

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

部署后需配置Uber OAuth应用的重定向URL为：
`https://`*{您的应用名称}*`.herokuapp.com/submit`
同时设置环境变量 FLASK_DEBUG=False 以正确提供SSL服务

API请求说明
---------------

所有请求基础URL：https://api.uber.com/v1/
完整端点列表请访问：https://developer.uber.com/v1/endpoints/
==============================