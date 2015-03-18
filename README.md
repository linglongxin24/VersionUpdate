# VersionUpdate
android 版本自动升级框架

先看效果
![image](https://github.com/linglongxin24/VersionUpdate/blob/master/20140721103828975.png)
使用
...java
package com.ydl.versionupdate;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.view.Menu;
import com.ydl.appupdate.NewVersion;

public class MainActivity extends Activity {
	private Context context = this;
	private String downloadPath = "http://192.168.0.116:8080/";
	private String appVsrsion = "android_version.json";

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		try {
			 new NewVersion(context, downloadPath,
						appVsrsion).checkUpdateVersion();
		} catch (Exception e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

	@Override
	public boolean onCreateOptionsMenu(Menu menu) {

		getMenuInflater().inflate(R.menu.main, menu);
		return true;
	}
}

服务器json文件内容

[{"app_name":"版本自动更新测试","apkname":"PassportSearch.apk","versionCode":"2","versionName":"1.0.1","apksize":"277883","apkinfo":"1,新增了登录注册功能。\n1,修复了部分bug!"}]

