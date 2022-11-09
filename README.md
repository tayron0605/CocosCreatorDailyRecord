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
# 2022.7.8
1.facebook登陆问题：安卓aab包经过上传Google play下载的apk包会被二次签名，需要把Google后台的.der证书下载下来通过keytool指令加入原本的keystore，然后将新的keystore生成密钥散列填入facebook后台
2.jdk和openssl库路径加入系统环境变量
# 2022.8.23
1.ccc2.4.9原生native下skeleton没有getTextureAtlas接口，getAttachment返回对象也没有region成员，会报错卡死
2.ADMob广告返回内部错误nofill检查一下vpn，改为美国纽约节点
# 2022.9.19
1.ccc2.4.9用了ParticleSystem3D要注意TrailModule,源码中cc.ParticleSystem3D.prototype.onLoad要判断一下if(this.trailModule.enable) this.trailModule.onInit(this);在new Pool的时候有大量GC开销所以要判断是否开启再init
# 2022.10.26
1.定制原生引擎 spine局部换肤
     a.python27需要32位版本(并配置环境变量PYTHON_BIN)
     b.pyyaml安装
     c.Cheetah-2.4.4.tar.gz安装
     d.NDK_ROOT环境变量配置
     e.修改SkeletonRenderer.cpp、SkeletonCacheAnimation.cpp、jsb-spine-skeleton.js(新增updateRegion方法)
     f.python执行genbindings.py
# 2022.11.5
1.原生spine二进制加载闪退
     a.修改SkeletonBinary.cpp的readAttachment方法
     b.在有皮肤的spine加载会有问题 要先保证readFloat全部读完 游标移位 否则region为NULL会有问题
     c.详细在官方fix spine binary data read issue. #4229这个pr中
# 2022.11.9
1.spined的setEventListener底层是addlistener,对象销毁时记得getState().removelistener()
