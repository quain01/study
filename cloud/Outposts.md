# outposts

- 本地部署，低时延、本地数据安全、业务迁移过程中的过渡（这个观点第一次看到）
- 跟公有云一致的体验，API、工具、管理界面
- 整机柜形态，42U机柜，单柜起步，扩展到96柜；21年推出1U/2U服务器形态
- VMWare版的Outposts也会很快推出

## 入门

1. 第 1 步: 创建 Outpost，首先创建一个 Outpost。
2. 第 2 步: 订购容量，从 Outposts 目录中选择一种配置，然后提交订单。AWS 会将 Outpost 配送到您的场地并为您安装。
3. 第 3 步: 创建子网，创建一个子网，并将其与您的 Outpost 关联。
4. 第 4 步: 启动实例，使用子网启动实例并在 Outpost 中创建卷。

![Outposts场地](img/outpost-changdi.png)

参考：

- [Outpost Console](https://ap-southeast-1.console.aws.amazon.com/outposts/home?region=ap-southeast-1#Home)
- [Outpost产品介绍](https://aws.amazon.com/cn/outposts/?nc2=h_ql_prod_cp_out)

