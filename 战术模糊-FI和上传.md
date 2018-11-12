# Tactical Fuzzing  -  FI和上传

## 包含本地文件

核心思想：它（或者它可以）与服务器文件系统交互吗？

[Liffy]（https://github.com/rotlogix/liffy）是新的，很酷，但你也可以使用[Seclists]（https://github.com/danielmiessler/SecLists/blob/master/Fuzzing/JHADDIX_LFI。文本）：

## 恶意文件上传

在这种类型的测试中，这是一个重要且常见的攻击向量。
文件上传功能需要大量保护才能充分保护。

攻击：
- 上传意外的文件格式以实现代码exec（swf，html，php，php3，aspx，++）Web shell或...
- 通过相同类型的文件执行XSS。图像也是！
- 通过将有效负载存储在元数据或文件头中，将解析器攻击到站点或XSS
- 绕过安全区域并通过文件多字符串将恶意软件存储在目标站点上

文件上传攻击是一个完整的演示。试试这个可以了解旁路技术：
- 内容类型欺骗
- 扩展技巧
-  [在洞中档案！presentaion]（https://www.nds.rub.de/media/attachments/files/2012/11/File-in-the-hole.pdf）

作为引用文件，polyglots可用于在服务器上存储恶意软件！
[见@dan_crowley的演讲]（http://goo.gl/pquXC2）
[和@angealbertini研究：]（corkami.com）

## 远程文件包含和重定向

查找包含其他网址的任何参数。LFI的相同参数也可以在这里出现。

常见的黑名单旁路：
- 使用“\ /”转义“/”或使用“\ / \ /”转义“//”
- 尝试单个“/”而不是“//”
- 删除http即“continue = // google.com”
- “/ \ / \”，“| /”，“/％09 /”
- 编码，斜杠
- “。/“ 改成 ”..//”
- “../“ 改成 ”....//”
- “/“ 改成 ”//”

重定向通用参数或注入点￼：
-  dest =
- 继续=
- 重定向=
-  url =（或其中包含“url”的任何内容）
-  uri =（与上述相同）
-  window =
- 下一个=

RFI通用参数或注入点：
- 文件=
-  document =
- 文件夹=
-  root =
- 路径=
-  pg =
-  style =
-  pdf =
-  template =
-  php_path =
-  doc =
