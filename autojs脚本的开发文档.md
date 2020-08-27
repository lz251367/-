### 移动类

* setScreenMetrics(width, height)  设置脚本适配

  > width , height 屏幕的宽度和高度，只要设置了会自动适配

* press(x, y, duration)  按下 api

  > x 、y 轴坐标  duration 模拟按下时间

* swipe(x1, y1, x2, y2, duration) 滑动 api

  > x1 y1 起始点坐标  x2 y2 终点坐标  duration 模拟滑动时间



### 设备类

* device.getBrightness()  当前屏幕的亮度
* device.getBrightnessMode()  返回当前亮度模式，0为手动亮度，1为自动亮度
* device.setBrightness(b)  修改当前亮度 手动，自动该函数无效  0~250
* device.setBrightnessMode(mode)  切换亮度模式  0为手动亮度，1为自动亮度
* device.getMusicVolume()  返回当前媒体音量。
* device.getNotificationMaxVolume()   返回通知音量的最大值。
* device.setMusicVolume(volume)  设置当前媒体音量。
* device.isScreenOn()  返回设备屏幕是否是亮着的  boolean
* device.wakeUp()  唤醒屏幕
* device.keepScreenDim([timeout])  唤醒屏幕常亮  常亮建议将 timeout 时间设置长 ，或者不设
* device.cancelKeepingAwake()  取消屏幕唤醒状态
* device.vibrate(millis)  手机振动  millis 多少秒
* device.cancelVibration()  如果处于振动就取消振动 



### 全局通用方法

* sleep(n)  暂停运行n毫秒的时间。
* setClip(text)  设置剪贴板里面的内容
* getClip()  返回系统剪贴板的内容。
* toast(message)  以气泡显示信息message几秒
* exit()  脚本停止运行
* random(min, max)  返回随机数  默认返回0 ~ 1



### APP相关

* app.launchApp(appName)  通过应用名称启动应用 返回值为boolear
* app.getPackageName(appName)  获取应用名称对应的已安装的应用的包名。找不回返回null
* app.openAppSetting(packageName)  打开应用的详情页(设置页)  返回值boolear
* app.viewFile(path)  用其他应用查看文件 找不可以查看抛异常
* app.editFile(path)  用其他应用编辑文件  找不可以编辑抛异常
* app.uninstall(packageName)  卸载应用。执行后会会弹出卸载应用的提示框
* app.openUrl(url)  用浏览器打开网址

