##	ReactNative环境搭建及MapBox for  ReactNative的简单使用
博客地址：https://blog.csdn.net/u011320682/article/details/86518024
###	本文以Mac为例，搭建ReactNative完整原生开发环境；
ps:上网查了查，好像国内用RN的做Mapbox的公开资料很少啊，貌似领先了一个车位？滴 学生卡~
#####	react native中文网：<https://reactnative.cn/docs/getting-started.html>
######	开发平台macOS，目标平台：android；
 	
没有安装homebrew的可以点击：[参考链接](https://www.jianshu.com/p/4e80b42823d5)
本项目代码：稍后更新github地址
 	
 1.  打开iTerm，执行：
 		`brew install node`
 		`brew install watchman`
 		安装完成后，执行命令查看node和watchman版本，如图所示：	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117095740881.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_5,color_FFFFFF,t_70)		 						

 2.  插件安装：
        官方建议Node安装完成后设置npm镜像以加速后边的过程（或使用科学上网工具）:
 		>npm config set registry https://registry.npm.taobao.org --global
 		>npm config set disturl https://npm.taobao.org/dist --global
 		
		执行：`npm install -g yarn react-native-cli`
 		Yarn安装完后也要设置镜像源（facebook提供替代npm工具，npm yarn二选一即可）；
 		>yarn config set registry https://registry.npm.taobao.org --global
		>yarn config set disturl https://npm.taobao.org/dist --global
		
		安装完成后在iTerm中输入-v通过查看版本，判定是否安装成功，如图所示：

      ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117102041841.png)
 3.  java和android studio的安装及环境配置此处略过。有一个需要注意的地方是ReactNative
 需要通过环境变量知道你的android sdk 安装的什么路径， 所以需要将如下内容添加到.bash_profile中；
 ⚠️如果你不是通过Android Studio安装的sdk，则其路径可能不同，请自行确定清楚。
`export ANDROID_HOME=$HOME/Library/Android/sdk`
`export PATH=$PATH:$ANDROID_HOME/tools`
`export PATH=$PATH:$ANDROID_HOME/tools/bin`
`export PATH=$PATH:$ANDROID_HOME/platform-tools`
`export PATH=$PATH:$ANDROID_HOME/emulator`
添加完成后，使用source命令来生效你所修改的设置。
 4.  打开iTerm，依次执行
	`mkdir RNProjects`
	`cd RNProjects`
	`react-native init DemoHello`
	通过adb devices查看设备是否在线及ls命令查看文件目录，确保无误后；
	执行`react-native run-android`,会开启js server，如图所示：
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117110031995.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117103800152.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
![测试机截图](https://img-blog.csdnimg.cn/20190117103957991.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 5.  ios运行同理，在iTerm中进入到项目，然后输入`react-native run-ios`即可；
 	  到这里ReactNative的开发环境和HelloWorld编写完成。
####	Mapbox的接入
 1. IDE选择的是 VScode，下载地址：https://code.visualstudio.com/
	安装完成后打开VScode，添加reactnative插件，安装后重启VScode，如图所示：
	![在这里插入图片描述](https://img-blog.csdnimg.cn/2019011710551255.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 2. react-native-mapbox-gl 下载地址：[Demo链接](https://github.com/mapbox/react-native-mapbox-gl)
 git下载地址：`git clone git@github.com:mapbox/react-native-mapbox-gl.git`
 安装所需sdk(二选一)：
 Yarn：`yarn add @mapbox/react-native-mapbox-gl`
 Nom：`npm install @mapbox/react-native-mapbox-gl --save`
 3. VScode导入项目，在example目录下创建accesstoken文件，将mapbox官网登陆后的key输入后保存，如图所示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117112418693.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 4. 打开Vscode中Terminal，cd进入到example目录中，然后执行 npm i，会安装node_models依赖；
 	⚠️在执行npm i之前必须确保已经添加accesstoken文件并将mapbox官网给的key输入其中，否则会报错无法找到access_token；
 	出现蓝色的reactnative的小图标表示安装完成，如图所示：
 	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117113903383.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117122448227.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 5. 按照官方教程依次修改／添加：
 	project：build.gradle
	```
	allprojects {
	    repositories {
	        jcenter()
	        maven { url "$rootDir/../node_modules/react-native/android" }
	        maven { url "https://jitpack.io" }
	        maven { url "https://maven.google.com" }
	    }
	}
	```
	app：build.gradle
	```
	dependencies {
    	compile project(':mapbox-react-native-mapbox-gl')
	}
	```
	settings.gradle
	```
	include ':mapbox-react-native-mapbox-gl'
	project(':mapbox-react-native-mapbox-gl').projectDir = new File(rootProject.projectDir, '../node_modules/@mapbox/react-native-mapbox-gl/android/rctmgl')
	```
	MainApplication.java
	```
	import com.mapbox.rctmgl.RCTMGLPackage;
	@Override
    protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
          new MainReactPackage(),
          new RCTMGLPackage()
      );
    }
	```
	⚠️按照上述代码添加完成后保存，一定要按照官方的提示一步一步走：~~（我就这里走偏了，直接执行`ract-native run-android`，然后报错`Android project not found. Maybe run react-native android first?`，StackOverflow有个答案说让执行`react-native upgrade`，然后yes更新就行了，这个坑掉进去好半天才爬出来。）~~ 
	运行 `npm start`
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117142600808.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
	打开Android Studio，选择导入项目（导入example文件夹中的android）
	下图这个就是通过gradle去构建ReactNative的项目，参照官网：
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117142959296.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117142831968.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 		点击ok后，Android Studio开始Gradle编译，不出意外完成后报错；
 		![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117143508164.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 		错误原因是distributionUrl会执行当前项目中的版本版本，而Android Studio会执行默认的gradle插件版本，gradle插件版本会影响build脚本，因对应关系失败，会导致该异常；
 		所以说了半天，改成`distributionUrl=https\://services.gradle.org/distributions/gradle-3.3-all.zip`重新编译就行了；
 		关于这部分可以参考资料：https://developer.android.com/studio/releases/gradle-plugin
 6. Android Studio 编译通过后，回到VScode Terminal，执行`react-native run-android`，可以看到Terminal 提示 BUILD SUCCESSFUL, 小窗口index.android.js 100%开启成功如图：
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019011715061584.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/2019011715063143.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117151015732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 7. ios 运行，执行`react-native run-ios`,报错`undefind is not an object()....`，删除ios文件夹的build文件，重新编译后运行成功。至于为什么重新编译后在运行就可以，我也不太清楚，有ios大佬告知一下原由么，感谢！
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190117152250499.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTEzMjA2ODI=,size_16,color_FFFFFF,t_70)
 9.  至此关于ReactNative环境搭建及MapBox在ReactNative简易教程结束；

