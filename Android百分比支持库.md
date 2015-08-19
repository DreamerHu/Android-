#Android百分比支持库介绍及使用步骤

1）获取支持库

	使用Android Studio在build.gradle添加一下信息就可以获取支持库，如果你没有下载到该支持库会提示你下载。
	
	dependencies{
		compile 'com.android.support:percent:22.2.0'
	}
	在Eclipse中使用需要在Android SDK　Manager里面升级extras里的Android Support Library,然后把更新import进项目工程里面，设置isLibrary 在项目中引用该Library

2）新的布局组件
	
	在这个包里有两个新的容器类：
	1、android.support.percent.PercentRelativeLayout
	2、android.support.percent.PercentFrameLayout
	由两个类的名称可以看出这两个类的父类分别是RelativeLayout、FrameLayout

3）新的属性设置
	
	新的容器增加了一下按照百分比来设置的属性
	1、layout_widthPercent 
		设置控件宽度为父容器宽度的百分比
	2、layout_heightPercent
		设置控件高度为父容器高度的百分比
	3、layout_marginPercent
		设置控件与周边控件的距离为父容器的宽度的百分比
4）使用介绍
	
	1、在布局的xml文件添加一下声明
		xmlns:app="http://schemas.android.com/apk/res-auto"
	2、在布局文件中使用想用的布局（使用时要使用包名+类名）
		<android.support.percent.PercentRelativeLayout>
			<ImageView
				app:layout_widthPercent="50%"
				app:layout_heigthPercent="50%"
				app:layout_marginTopPercent="25%"
				app:layout_marginLeftPercent="25%"
			/>
		</andoid.support.percent.PercentRelativeLayout>
		
		

	