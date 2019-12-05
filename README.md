# TopRightMenu


类似手机QQ界面右上角的弹出菜单，使用`recyclerview`和`popupwindow`封装了一下.

效果图： 


![](https://github.com/cnlisn/TopRightMenu/blob/master/img/screenshot-1575528189483.jpg)


# Install

Gradle:

```groovy
compile 'com.lisn:toprightmenu:1.0.0'
```



or 下载library手动导入.

# Usage

```java
mTopRightMenu = new TopRightMenu(MainActivity.this);

//添加菜单项
List<MenuItem> menuItems = new ArrayList<>();
menuItems.add(new MenuItem(R.mipmap.multichat, "发起多人聊天"));
menuItems.add(new MenuItem(R.mipmap.addmember, "加好友"));
menuItems.add(new MenuItem(R.mipmap.qr_scan, "扫一扫"));

mTopRightMenu
        .setHeight(480)     //默认高度480
        .setWidth(320)      //默认宽度wrap_content
        .showIcon(true)     //显示菜单图标，默认为true
        .dimBackground(true)        //背景变暗，默认为true
        .needAnimationStyle(true)   //显示动画，默认为true
        .setAnimationStyle(R.style.TRM_ANIM_STYLE)
        .addMenuList(menuItems)
        .addMenuItem(new MenuItem(R.mipmap.facetoface, "面对面快传"))
        .addMenuItem(new MenuItem("id", R.mipmap.pay, "付款"))
        .setOnMenuItemClickListener(new TopRightMenu.OnMenuItemClickListener() {
              @Override
              public void onMenuItemClick(int position) {
                  Toast.makeText(MainActivity.this, "点击菜单:" + position, Toast.LENGTH_SHORT).show();
              }
        })
        .showAsDropDown(moreBtn, -225, 0);	//带偏移量
//      		.showAsDropDown(moreBtn)
```
