# IBM-CF-AutoPush

使用它定期将最新的 V2Ray 部署至 IBM Cloud Foundry



## Fork 本仓库

Fork it!



## 设置变量

点击项目下方最后一枚 Settings 按钮

选中左侧 Secrets 后右上角 点击 New secret

在界面中添加如下变量：


  ACCOUNT     ==>   IBM 账户邮箱

  PWD         ==>   IBM 账户密码

  REGION      ==>   Cloud Foundry 应用地区 (一般就是 us-south (达拉斯)

  与域地址是 us-south.cf.appdomain.cloud 还是另选了 mybluemix.net 无关

  APP_NAME    ==>   应用程序名, 区分大小写

  UUID        ==>   V2Ray配置中的 UUID, 以后需要更换直接 update 此 secret 即可



## 激活 Actions

点击项目下方第三枚 Actions 按钮

点击 "I understand my workflows, go ahead and enable them"

回到 Code 界面

中间上方 Add file -> Create new file -> 随便起个名 -> Commit new file

回到 Actions 即可看到它跑起来了



## 自定义时间

#### 本项目默认每周一 5:00am 执行 IBM Cloud Foundry 的自动部署

修改 Code 栏此路径下的 .yml 文件

- IBM-CF-AutoPush/.github/workflows/

自定义第九行中的内容即可

```
$ - cron: '0 21 * * 0'
```

注: 该处采用 UTC 时间
