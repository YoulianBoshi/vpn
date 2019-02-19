
Lantern shared VPN network to mobile phone use

蓝灯如何共享VPN网络至手机使用教程

一：查看自己电脑网卡IP地址，以Windows10专业版为例

方法1：打开设置--打开网络和Internet--选择WLAN--点击WiFi名称往下拉即可查看本机IP地址

![](https://telegra.ph/file/ba92f289a476da1cc5945.png)

![](https://telegra.ph/file/7e942401f6d425b34b0f4.png)

![](https://telegra.ph/file/925af02b7b2c88b4b7c7d.png)

方法2：在桌面上按“Win+R”组合键--输入“CMD”--然后回车键

![](https://telegra.ph/file/a077ab011e738a24fac72.png)

输入此命令：“ipconfig/all” --然后回车键

![](https://telegra.ph/file/484abfcf846fcbf851b8d.png)

直到出现此页面

![](https://telegra.ph/file/6cf7715d2b2b9ba41f3bf.png)

可以看到你的网卡IP地址为：XXX.XXX.XXX.XXX（首选），请记住IP地址

二：蓝灯：

1：右键lantern --属性

![](https://telegra.ph/file/90d1a7582dd45c966cd21.png)

在目标(T)|：lantern.exe末尾处加入： -addr XXX.XXX.XXX.XXX:8787，然后点击--应用，配置已经完成，这时你的电脑相当于一台小型服务器了

![](https://telegra.ph/file/c852dd11a24017444839b.png)

开启电脑移动热点

![](https://telegra.ph/file/3855b829cea4eae6fa73c.png)

重新启动蓝灯程序，打开手机WiFi连接此移动热点，iOS/Android手机--输入密码--高级配置--代理--手动--代理服务器：XXX.XXX.XXX.XXX:8787--保存

![](https://telegra.ph/file/3358981ca6dbfc279d140.png)

手机设置成功后，你现在可以尽情地享受匿名的高速网上冲浪了！

【注意】：蓝灯在PC端必须保持运行，否则无法正常使用，切换至英文输入避免出错，电脑和手机在同一WiFi路由器情况下如同以上操作无需电脑开启热点即可走蓝灯路线，若不再想继续使用蓝灯路线则需要删除手机WiFi所进行的配置即可恢复正常

![](https://telegra.ph/file/5d9ad3b0b61b37c61bc58.png)

谢谢您的赞赏，谢谢您的支持！

![](https://telegra.ph/file/7fef1213486fe3f2ce222.png)  ![](https://telegra.ph/file/6ace087355ae72a1314e2.jpg)  ![](https://telegra.ph/file/d4ddbbf7c920c92c72281.jpg)
