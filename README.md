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
