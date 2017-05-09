##如何使用：
Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Step 2. Add the dependency

	dependencies {
	        compile 'com.github.jeasinlee:FlowTag:1.0'
	}

# FlowTagLayout
Android流式布局，支持点击、单选、多选等，适合用于产品标签等，用法采用Adapter模式，和ListView、GridView用法一样！

2016/6/26号新添加初始化标签功能，使用非常简单，只要你的Adapter实现OnInitSelectedPosition即可，对于点击模式是不存在初始化标签一说的；对于单选模式来说，如果有多个初始化选择，则默认去第一个；对于多选来说正常使用！！！

****

##特色

* 填充数据和ListView、GridView用法一样使用Adapter，更新数据直接通过adapter.notifyDataChanged来更新
* 支持点击、单选、多选事件
* 三种模式：FLOW_TAG_CHECKED_NONE、FLOW_TAG_CHECKED_SINGLE、FLOW_TAG_CHECKED_MULTI
* 支持OnTagClickListener单点事件
* 支持OnTagSelectListener单选、多选事件

****

#效果图

![image](https://github.com/hanhailong/AndroidStudyResources/blob/master/screenshot/flow_tag.gif?raw=true)

#版本更新

##2016/6/26
* 添加初始化选中标签
    * 单选模式下初始化标签只有第一个起作用
    * 多选模式下只要设置初始化选中就可以
* 添加初始化选中标签代码示例
	 * Adapter实现OnInitSelectedPosition接口
	 * 实现接口中isSelectedPosition方法就可以，选中返回true，不选中默认返回false
	 
	 
			 public class TagAdapter<T> extends BaseAdapter implements OnInitSelectedPosition {
			 @Override
		    		public boolean isSelectedPosition(int position) {
		        	if (position % 2 == 0) {
		            	return true;
		        	}
		        	return false;
		    	}
			 }
    

