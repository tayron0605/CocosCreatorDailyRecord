# CocosCreatorDailyRecord
# 2021.11.30
1.FairyGUI GObject取.node出来的y和cocos的y是相反的
2.微信createUserInfoButton需要适配scale
     let screenInfo = wx.getSystemInfoSync();
     let visibleSize = cc.view.getVisibleSize(); 
     let widthScale = screenInfo.screenWidth/visibleSize.width;
     let heightScale = screenInfo.screenHeight/visibleSize.height;
     等宽-> return widthScale
     登高-> return heightScale
# 2022.5.27
1.热更新hot-update插件添加searchPath相关代码无效，需要手动在F:\CocosDashboard\resources\.editors\Creator\2.4.9\resources\static\build-templates\shares\main.js头部添加
# 2022.6.9
Cocos安卓native接谷歌和Facebook踩坑
1.aar引用相关问题
2.android studio Debug包用正式版签名问题
3.模拟器adb调试
4.android studio setting里面改代理端口 不然不能引入facebook和google库 gradle会报错(翻墙梯子)
5.google 12501问题(vpn)
6.jsb绑定注意返回String类型，cocos文档中参数介绍和代码示例中的Ljava/lang/String;不一样 有穿插空格 必须严格匹配
7.2.4.9安卓spine闪退问题 贴图要小于1024 并且是json不能用二进制
8.app的bundle.gradle修改大版本号versionCode和versionName
# 2022.6.10
1.安卓大版本更新迭代覆盖安装apk需要清理热更新可写目录 jsb.fileUtils.removeDirectory(jsb.fileUtils.getWritablePath());
