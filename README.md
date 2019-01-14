# 自己用到的第三方库
## 添加依赖库的方法
# 数据库
## [Greendao](https://github.com/greenrobot/greenDAO)
```
相关说明
	
```
## [LitePal](https://github.com/LitePalFramework/LitePal)
```
相关说明
	
```
## [android-lite-orm](https://github.com/litesuits/android-lite-orm)
```
相关说明
	
```


## Step 2. 添加依赖
### 最新版本号为:[![](https://jitpack.io/v/Brioal/BottomTabLayout.svg)](https://jitpack.io/#Brioal/BottomTabLayout)
```
	dependencies {
	        compile 'com.github.Brioal:BottomTabLayout:1.4'
	}
	
```

# 仿360底部动画菜单布局
# 效果对比:
360手机助手效果演示:|本库实现的效果(Icon来自360手机助手,侵删)
:--|:--
![](https://github.com/Brioal/BottomTabLayout/blob/master/art/2.gif)|![](https://github.com/Brioal/BottomTabLayout/blob/master/art/1.gif)
# 写在前面:
## 如果觉得效果还行请顺手点个sta支持一下r,谢谢
## 欢迎加入我创建的QQ交流群,群号:375276053

## 另外我的开源库:
## [多达288种动画效果定制的侧滑菜单库](https://github.com/Brioal/SwipeMenuDemo)
## [仿TC App加速效果](https://github.com/Brioal/MovingCircleView)
## 欢迎查看与star
# 使用方法:
## xml布局文件
## 注:为了美观,讲每个Button的高度以及固定,设置wrap_content时候是最大高度,为50dp,如果需要设置特定高度请参见下文的方法表格
```
    <com.brioal.bottomtab.view.BottomLayout
        android:id="@+id/main_tab"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true">

    </com.brioal.bottomtab.view.BottomLayout>

```
## 数据源添加与基本设置
```
mList = new ArrayList<>();
        mList.add(new TabEntity(R.mipmap.icon_1, "推荐"));
        mList.add(new TabEntity(R.mipmap.icon_2, "游戏"));
        mList.add(new TabEntity(R.mipmap.icon_3, "软件"));
        mList.add(new TabEntity(R.mipmap.icon_4, "应用圈"));
        mList.add(new TabEntity(R.mipmap.icon_5, "管理"));
        mBottomLayout.setList(mList); //设置数据源
        mBottomLayout.setNews(1, 0); //设置未读消息
        mBottomLayout.setNews(2, 1);
        mBottomLayout.setNews(3, 2);
        mBottomLayout.setNews(4, 3);
        mBottomLayout.setNews(5, 4);
        //设置Item点击事件
        mBottomLayout.setSelectedListener(new OnTabSelectedListener() {
            @Override
            public void onSelected(int position) {
                mBottomLayout.cleanNews(position); //清除未读消息
                if (mToast == null) {
                    mToast = Toast.makeText(MainActivity.this, position + "", Toast.LENGTH_SHORT);
                } else {
                    mToast.setText(position + "");
                }
                mToast.show();
            }
        });
```
## 这样设置之后的效果如示例图所以,已经可以基本使用,本库还提供其他自定义效果,如下:
xml属性|Java方法|功能
:--|:--|:--
`colorNormal`|`void setColorNormal(int colorNormal)`|设置未选中的时候Icon和文字的颜色
`colorSelected`|`setColorSelect(int colorSelect)`|设置选中的时候Icon和文字的颜色
`textSize`|`setTextSize(int textSize)`|设置字体的大小
`exCircleColor`|`setExCircleColor(int exCircleColor)`|设置外圆颜色
`inCircleColor`|`setInCircleColor(int inCircleColor)`|设置内圆颜色
`animDuration`|`setDuration(int duration)`|设置点击涟漪的动画时长
无|`void setList(List<TabEntity> list)`|设置数据源,格式为资源文件,菜单名称
无|`void setMenuHeight(int height)`|设置菜单高度,默认为50dp,适宜高度
无|`void setCurrentIndex(int currentIndex)`|设置选中的Tab按钮下表
无|`setSelectedListener(OnTabSelectedListener selectedListener)`|设置Item点击事件
无|`setNews(int newSum, int index)`|设置指定Item的未读消息数量
无|`cleanNews(int index)`|清除指定Item的未读消息

## 方法就这些,使用也不难.

# 
<!--获取运营商信息，用于支持提供运营商信息相关的接口-->
 <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" /> 
 <!--用于访问wifi网络信息，wifi信息会用于进行网络定位--> 
 <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" /> 
 <!--这个权限用于获取wifi的获取权限，wifi信息会用来进行网络定位--> 
 <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
 <uses-permission android:name="android.permission.CHANGE_CONFIGURATION" />
 <!-- 请求网络 --> 
 <uses-permission android:name="android.permission.INTERNET" />
 <!-- 更改设置 --> 
 <uses-permission android:name="android.permission.WRITE_SETTINGS" />
 <!--用于进行网络定位-->
 <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
 <!-- 可以提高室内定位的精确度 -->
 <uses-permission android:name="android.permission.BLUETOOTH_ADMIN" /> 
 <!-- 可以提高室内定位的精确度 --> 
 <uses-permission android:name="android.permission.BLUETOOTH" /> 
 <!--用于访问GPS定位--> 
 <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" /> 
 <!--用于提高GPS定位速度--> 
 <uses-permission android:name="android.permission.ACCESS_LOCATION_EXTRA_COMMANDS" /> 
 <!--写入扩展存储，向扩展卡写入数据，用于写入缓存定位数据--> 
 <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" /> 
 <!--读取缓存数据--> 
 <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
 <!--用于读取手机当前的状态--> <uses-permission android:name="android.permission.READ_PHONE_STATE" />
