## 框架介绍

本框架主要是基于 Python + pytest + allure + log + yaml + mysql + redis + 飞书/钉钉/企微/Email通知 + Jenkins 实现的接口自动化框架

本仓库仅作二次开发库，具体使用请移步原作者仓库git地址: [https://gitee.com/yu_xiao_qi/pytest-auto-api2](https://gitee.com/yu_xiao_qi/pytest-auto-api2)

**环境配置**  

1. 配置环境Python 3.8  

2. 下载并配置jdk环境变量  
https://www.injdk.cn/?utm_source=testingpai.com  

3. 下载allure放在`C:\Program Files\allure-2.29.0`，然后配置环境变量PATH=`C:\Program Files\allure-2.29.0\bin`  
https://github.com/allure-framework/allure2/releases  

4. 先检查allure命令是否能正常运行，如果编辑器无法识别allure命令，可以使用管理员方式打开编辑器  

Allure显示乱码相关问题:  
https://blog.csdn.net/weixin_43865008/article/details/124332793  


**执行步骤**
```
python -m venv .venv
source .venv/Scripts/activate
pip install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple/
执行test.py文件
```

**实现功能**

测试数据隔离, 实现数据驱动  
支持多接口数据依赖: 如A接口需要同时依赖B、C接口的响应数据作为参数  
数据库断言: 直接在测试用例中写入查询的sql即可断言，无需编写代码  
动态多断言: 如接口需要同时校验响应数据和sql校验，支持多场景断言  
自动生成用例代码: 测试人员在yaml文件中填写好测试用例, 程序可以直接生成用例代码，纯小白也能使用  
代理录制: 支持代理录制，生成yaml格式的测试用例  
统计接口的运行时长: 拓展功能，订制开关，可以决定是否需要使用  
日志模块: 打印每个接口的日志信息，同样订制了开关，可以决定是否需要打印日志  
钉钉、企业微信通知: 支持多种通知场景，执行成功之后，可选择发送钉钉、或者企业微信、邮箱通知  
自定义拓展字段: 如用例中需要生成的随机数据，可直接调用  
多线程执行  
支持swagger接口文档转成yaml用例，节省用例编写时间  
