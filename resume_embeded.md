# 徐宪辉

## 软件工程师

- 联系电话: +86 18682002664
- 电子邮箱: [saw1993@126.com](saw1993@126.com)


## 自我描述

我是一名热爱技术的软件工程师，有着丰富的项目研发和管理经验，熟悉嵌⼊式、Android，了解iOS和后端。

我极其注重**设计模式**，**编码规范**以及**开发效率**；当然，作为一名程序员，我也很注重数据结构和算法。


## 工作经验

### **软件经理** [深圳市好上好信息科技股份有限公司]

*2020/3 - 至今*

#### 负责**Lora手表**的**产品研发**, 此项目使用华大MCU，系统为FreeRTOS，有LCD屏，Lora，FC，外部Flash，等硬件。项目主要内容如下：
* 针对不同类型的模块进行分层，使得代码耦合更低，可维护性更强。
* 使用进入读写SPI时进入临界区的方法解决了多个SPI设备使用使用同一条SPI导致的冲突问题；
* 通过给需要在主循环钟添加代码的设备添加task，实现了不同设备与主循环的解耦；
* 使用低功耗Timer来定期唤醒MCU，实现了待机时可通过Lora接收数据的功能；
* 通过加入Boot，并实现了USB CDC升级功能，实现了对App层进行固件升级的功能；
* 通过在中断函数中使用信号量和Notify，从而降低了业务逻辑的复杂度，提高了代码的可读性和可维护性；
* 使用PWM控制LED灯，实现了可调亮度的功能；
* 集成了Emwin，方便进行UI绘制与文字显示；
* 使用单向链表，实现了灵活的调频测试功能，频率范围，间隔频率，频率持续时间，发射功率等参数皆可轻松修改；
* 使用keil target功能实现了对24M晶振和32M晶振两版硬件的快速切换；

#### 负责**BLE运动手环**的**产品研发**，此项目使用Nordic 52810作为主控，通过I2C控制ST 6轴传感器(加速度，陀螺仪)：
* 通过Nordic的Scheduler库实现了中断函数内的标志位和Main Loop的解耦；
* 通过i2c读取了传感器的数据，然后通过Ble Notify传给了App。
* 通过在启动时检测按键是否持续按下，实现了假长按开机功能，避免了一碰到按键就开机的问题。

#### 负责多个**BLE透传模块**的**产品研发**，以及与客户对接，修复Bug和按照客户需求新增功能，项目主要内容如下：
* 使用AT指令，实现扫描，连接，传输数据等基本功能；
* 通过引入了Git管理项目，从而规范了开发流程；
* 通过标准化连接流程，从而修复了GATT连接兼容性差的问题；
* 使用keil中的Target功能，实现了开发板固件和量产固件的一键切换，而不需要修改多个配置；
* 使用keil中的AfterBuild脚本功能，实现了自动合并App Hex和Softdevice Hex；


#### 负责**Lora模块**的**维护**，主要内容如下：
* 通过增加配置用的宏定义，实现了对不同配置之间的快速切换。
* 通过提取开发中的公共组件模块，合理分类并封装它们，从而提了升组件的复用性。
* 通过引脚选择，实现有着不同功能的模式。

#### 负责**蓝牙模块DFU App**的编写，代码全部使用Kotlin编写，可全自动对BLE模块进行DFU升级，主要内容如下：

* 修改Nordic DFU Library的使用方式，实现了非标准的DFU程序的蓝牙模块的升级。
* 使用属性代理的方式加载部分需要懒加载的对象，降低了代码的耦合。
* 使用LiveData进行了数据的绑定，从而使得UI上的数据能够自动刷新。



### **软件经理** [深圳市大豆电子有限公司]

*2017/6 - 2020/3*

#### 负责**BLE Mesh电源**的**研发管理**与**技术选型**以及**疑难杂症解决**，主要内容如下：

* 负责Review Code，处理开发人员的Merge Request，保证代码质量；
* 引入敏捷开发流程，方便项目管理；
* 指定编码规范，更利于维护项目，提高开发效率；
* 实现电源Firmware的渐变PWM调光方式，提高产品使用体验；
* 负责制定Mesh电源等配套传感器的配置和控制的协议；
* 优化协议，把Mesh网络中的节点数量从20提高到了500+，场景数量提高到100；
* 优化MeshSDK，提高设备入网速度以及对华为手机的兼容性；
* 主导从跨平台方案(APICloud)切换到原生方案，蓝牙兼容性问题更易处理；
* 负责Android端技术选型；大范围使用Rxjava系列库降低代码复杂度；
* 负责新的BLE MESH IC 的选型。

#### 负责AirTranslator APP的开发，此项目是一个**搭配TWS耳机的翻译APP**：
* 使用Nuance SDK实现ASR和TTS的功能；
* 使用环信实现了IM方面的功能，包括群聊、语音聊天、表情等功能；
* 实现了根据需要从不同设备输出音频的功能，比如时而从TWS耳机，时而从手机扬声器；

#### 负责**Android系统长条屏广告机App**的编写，主要内容如下：
* 使用Rxjava+Retrofit从服务器获取数据Json，异步下载图片/视频，并使用combine合并请求，确保已全部加载完成。
* 使用Rxjava订阅已下载的节目数据，在Program, Page,Element,Video/Image 环环相扣的数据结构下，实现了快速切换订阅源，以及清晰的数据解析功能；
* 实现了同屏同时播放多个视频，第一个视频直接硬解，第二个视频通过使用基于ffmpeg的ijkplayer库进行软解，从而实现同屏同时播放多个视频；


### **FAE** [深圳市北高智电子有限公司]

*2013/11 - 2017/06*

#### 负责**Sensortek Gsensor产品线**的技术支持
* 帮助客户调整 sensor linux kernel代码，兼容对应平台；
* 帮助客户调整 hal 层代码，提⾼使⽤效果;
* 通过调整参数，解决 Z 轴偏移过大的问题;

#### 负责**Memsic Msensor产品线**的技术支持
* 帮助客户集成发现算法，创建虚拟的方向传感器；
* 调整参数适配不同的板子，提高Sensor准确度；
* 协助用户集成Memsic的守护进程。

#### 负责**UEI 万能红外遥控器** 产品线的技术支持
* 协助客户集成Android SDK，实现客户自定义APP与SDK的对接；
* 协助客户集成HAL SDK，实现Android标准 ConsumerIR接口；
* 帮助部分客户开发完整的遥控器APP；


## 技能专长

以下都是我比较熟悉和了解的一些技术。

### 编程语言

- Java
- C 
- Kotlin
- Python
- Objective C
- Swift
- Javascript


### 协议
- I2C
- SPI
- UART
- BLE
- BLE Mesh
- MQTT
- Lora

### 系统
- Android
- FreeRTOS

### 工具软件
- Android Studio
- Keil
- Visual Studio Code
- Make
- CMake
- Git
- Source Tree
- Git extension
- Adobe Premiere
- Adboe Audition

### 工具硬件
- 示波器
- 逻辑分析仪
- 频谱仪
- 万用表


## 教育经历

- *2016 - 2018* [国家开放大学] 软件工程 本科
- *2011 - 2014* [九江职业技术学院] 软件工程 大专


## 兴趣爱好

极客，对计算机和相关技术有狂热兴趣。

## 致谢

感谢您花时间阅读我的简历，期待能有机会和您共事。
