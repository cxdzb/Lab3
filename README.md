# 《WPF实现MIDI乐队APP》实验报告
#### 学院：软件学院  班级：2017级软工1班  学号：3017218062   姓名：刘书裴
#### 日期：  2019  年 4 月 11 日
## 一、功能概述
###### 1、点击open，选择音乐进行播放。
###### 2、可使用按钮进行开始/暂停/继续操作，也可使用进度条改变播放进度。
###### 3、中央列表储存着播放过的音乐，可显示当前播放的音乐。
###### 4、可选择播放模式（单曲循环/顺序播放/随机播放）。
###### 5、播放过程中对应的乐器也会作出对应的操作。

## 二、项目特色
###### 1、多种播放模式。
###### 2、可点击列表对应音乐继续播放。
###### 3、加入try-catch异常语句，防止意外错误的发生。
###### 4、实现了窗口自适应。

## 三、代码总量
无法计算

## 四、工作时间
无法计算

## 五、知识点总结图（Concept MAP）
![](https://github.com/cxdzb/Lab3/blob/master/Images/1.png?raw=true)

## 六、结论
#### 实验过程：

###### 1、实现控件和窗口的自适应
1)、定义Viewbox，Stretch="Fill"。
2)、由于Viewbox只能有一个子对象，所以定义一个Canvas将所有内容包含在内。
###### 2、实现列表点击播放
1)、添加一个ListBox。
2)、编辑ListBox_SelectionChanged（选择项改变）事件，当选中音乐时，载入并播放此音乐。
3)、使用在open之前先调用stop方法避免死锁。
###### 3、实现播放模式选择
1)、添加3个RadioButton。
2)、定义play_method属性用于储存播放模式。
3)、3个RadioButton公用RadioButton_Checked事件，默认为顺序播放，当选择某个模式时，play_method随之改变。
###### 4、实现多种播放模式
1)、定义当前播放的音乐及其索引。
2)、在HandlePlayingComplete事件中调用play，使用Dispatcher.BeginInvoke异步调用play。
3)、创建play函数，判断播放模式。对于循环播放，即播放列表中下一首；对于随机播放，使用随机数选择音乐；对于单曲循环，即重新播放当前音乐。
#### 实验结果：
###### 1、刚打开程序时
![](https://github.com/cxdzb/Lab3/blob/master/Images/2.png?raw=true)

###### 2、改变形状时
![](https://github.com/cxdzb/Lab3/blob/master/Images/3.png?raw=true)

###### 3、将音乐加入列表
![](https://github.com/cxdzb/Lab3/blob/master/Images/4.png?raw=true)
