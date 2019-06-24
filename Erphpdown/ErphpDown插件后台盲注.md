## ErphpDown插件后台盲注

在erphpdown/admin/action/vip.php中第13行中接收了请求中的id参数，虽然在escape方法中已经过滤了单双引号反斜杠等等，但是在15行中进行sql语句的拼凑时，并没有用单引号将id参数包含住，也就是我们构造sql注入时并不需要单引号，过滤也就没有什么意义了。

![1560845669675](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560845669675.png)

## 复现：

![1560848303920](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560848303920.png)

![1560848323799](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560848323799.png)



同样的问题还存在于order.php中

![1560848703139](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560848703139.png)
