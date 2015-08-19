#ActionBar和ToolBar介绍及用法


## （一）ActionBar介绍 ##

1. 在Android3.0之后，Google对UI导航设计进行了一系列改革，其中就引用了一个新功能ActionBar，它用于取代3.0之前的标题栏，并且提供了丰富的导航效果。

## （二）ActionBar的使用 ##


1. 添加ActionBar

	（1）. ActionBar不需要开发者导入，在Android3.0及3.0以上的版本中，项目的Activity中已经默认包含有ActionBar

	（2）. 将项目的android:minSdkVersion或者android:targerSdkVersion的属性设置成11或者更高，则该应用程序会默认包含ActionBar
2. 隐藏ActionBar
	
	（1）. 我们可以通过把主题设置成Theme.Holo.NoActionBar去掉ActionBar
	
			<activity android:theme="@android:style/Theme.Holo.NoActionBar"/>

	（2）. 我们可以通过代码调用ActionBar中的show()和hide（）方法来控制ActionBar的显示和隐藏

			ActionBar actionBar=getActionBar();
			actionBar.show();//控制显示ActionBar
			ActionBar.hide();//控制隐藏ActionBar
3. 添加ActionBar的Item
	
	（1）. 通过代码动态添加重写onCreateOptionsMenu(Menu menu)方法
		
			@Override
		    public boolean onCreateOptionsMenu(Menu menu) {
		        super.onCreateOptionsMenu(menu);
				MenuItem add=menu.add(0,0,0,"add");
				MenuItem del=menu.add(0,0,0,"del");
				add.setShowAsAction(MenuItem.SHOW_AS_ACTION_IF_ROOM);
				add.setShowAsAction(MenuItem.SHOW_AS_ACTION_IF_ROOM);
		        return true;
		    }
	
	（2）. 通过menu.xml文件布局

			<menu xmlns:android="http://schemas.android.com/apk/res/android" >
	 
	   		<item
		        android:id="@+id/item1"
		        android:orderInCategory="1"
		        android:showAsAction="ifRoom|withText"
		        android:title="@string/save"/>
	    	<item
		        android:id="@+id/item1"
		        android:orderInCategory="2"
		        android:showAsAction="ifRoom|withText"
		        android:title="@string/edit"/>
			</menu>

## 
#（三）menu.xml中Item属性介绍 ##

1. android:showAsAction=""

	showAsAction总共有五个属性值：ifRoom、never、always、withText、collapseActionView，可以混合使用

		
		- ifRoom：会显示在Item中，但如果有4个或4个以上的Item时会隐藏在溢出列表中，当然个数不仅仅局限于4个，依据屏幕的宽窄而定
		- never：永远不会显示，只会在溢出列表中显示，而且只显示标题，最好把标题都带上
		- always：无论是否溢出，总会显示在屏幕上
		- withText：withText值示意ActionBar要显示文本标题。ActionBar 会尽可能的显示这个标题，但是，如果图标有效并且受到ActionBar空间的限制，文本标题有可能显示不全。
		- collapseActionView：声明了这个操作视图应该被折叠到一个按钮中，当用户选择该按钮时，这个操作视图展开。否则，这个操作视图在默认的情况下是可见的，并且即便在用于不适用的时候，也要占据操作栏的有效空间，一般要配合ifRoom一起使用才会有效
		
2. android：menuCategory=""
	
	(1)对菜单进行分类，定义菜单的优先级，有四个有效值：container、system、secondary和alternative；通过menuCategory属性可以控制菜单项的位置
	
		
		- container：
		- system：表示该菜单项是系统菜单，应该放在其他种类菜单项的后面
		- secondary：
		- alternative：

3. android:orderInCategory="2"
		
	（1）orderInCategory的值表示同种类菜单item的摆放顺序，该属性设置一个整数值，不一定从0开始计算，但必须大于等于0，数值小的位于前，如果数值一样，则按照摆放顺序，该值相当于menu.add()中的第三个参数的值，建议从0,1,2,3,4,5....这样依次设置值
4. android：checkable="true"

	checketable表示是否可选，有true和false两个值


5. android:enabled:设置菜单项是否可用 。

6. android：checked：是否已经被选中。

7. android:icon:菜单的图标。

8. android：title菜单标题字符串。

9. android：titleCondensed：浓缩标题，适合标题太长的时候使用。

10. android:alphabeticShortcut：字符快捷键。

11. android:numericShortcut：数字快捷键。


	
	
			
	

