# RegisterWxDemo
微信注册模块，将所在手机号与微信相关的数据上传

注册辅助app 流程

1.用户 填写输入框 pass，chn_id 内容

2.点击"上传现有wx数据并一键新机"按钮，app就

（1）停止微信app

（2）连接wifi，将原来为4G的网络变为连接wifi

（3）将数据上传到接口 http://192.168.0.213:8000/wechat/userInfoForOld （上传失败话，重试3次，还是失败的话 提示，并停止）

（4）清理微信数据

（5）断开wifi，开启飞行模式

（6）关闭飞行模式，连回4G

 (7) 随机应用变量，保存

 (8）显示完成



需要注意的，因为这次是真机运行的，所以第一步杀死微信进程，不能直接用adb shell 的方式来执行命令，需要借助I/O流的形式来做，这样其实就是写一个壳来运行adb 指令。然后就是读取文件时，因为是xml的string虽然也是key-value的形式，但是不能直接用element.attributeValue("value")来拿收据，而是通过 element.getStringValue();来获取到String的值。





