# Cuttlefish
简单封装QQ、微信、微博的登录、分享功能

###初始化配置
```
Config.get()
//obligatory
.qq("appId", "appKey").wechat("appId", "appKey").weibo("appId", "appKey")
//optional
.qqScope("scope").wechatScope("scope").weiboRedirectUrl("url").weiboScope("scope");
	
```

#####微信
```
在程序包名根新建继承AbsWXEntryActivity的Acitivty，并配置到AndroidManifest.xml。

```


###登录
```
QQ登录	

Cuttlefish.with(context).login()
.callback(mLoginResultCallback).to(QQLoginHandler.get())
```

###分享
```
QQ分享
Cuttlefish.with(context).share()
            .appName("Cuttlefish")
            .title("Title")
            .description("Description")
            .content("Content")
            .image("imagePath")
            .link("http://link...").callback(mShareResultCallback).to(QQShareHandler.get(QQShareHandler.QZONE));
```

###Gradle
1.Add it in your root build.gradle at the end of repositories:

```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

```
2.Add the dependency

```
dependencies {
            compile 'com.github.XMXu.Cuttlefish:library:v1.1'
            compile 'com.github.XMXu.Cuttlefish:handlers:v1.1'
}
```

#####更多详情见[app](https://github.com/XMXu/Cuttlefish/tree/master/app)
