# luobo-android
## 开发环境配置 

### Android Studio 
[下载地址](https://developer.android.google.cn/studio/index.html?hl=zh-cn)

#### 插件安装 
打开Settings>Plugins>Browse Repositories安装： 

1. **FindBugs-IDEA**  
Java代码的静态检查工具。安装后重启，在Settings中找到和选中FindBugs-IDEA选项，在Plugins中勾选Findbugs plugin for Android启用Android的代码检查，在Filter里Exclude filter files中添加项目根目录下的findbugs-android-exclude.xml，这是需要跳过检查的文件配置。 

2. **Android Parcelable code generator**  
自动生成Parcelable接口实现的工具。使用方法是在需要实现Parcelable的类中，右键选中Generate>Parcelable>OK

未完待续...

## 测试环境配置

### [BatteryHistorian安装和使用](https://coding.net/t/luoboshuzhai/p/luobo-android/git/blob/zhengxingtian/battery-historian-guide.md)

### [Monkey脚本的使用](https://coding.net/t/luoboshuzhai/p/luobo-android/git/blob/zhengxingtian/monkey-test-guide.md)

### [Appium的安装和使用](https://coding.net/t/luoboshuzhai/p/luobo-android/git/blob/zhengxingtian/appium-guide.md)

## 推荐阅读的书籍列表
- Java
    * 《Thinking in java》
    * 《Effective java》
    * 《深入理解Java虚拟机》
    * 《Java并发编程的艺术》
- Android
    * 低难度
        - 《Android4高级编程》
    * 中难度
        - 《Android C++高级编程 使用NDK》
        - 《Android应用性能优化》
        - 《Android开发高手进阶》
        - 《深入理解Android 卷3》
        - 《Android群英传》
        - 《SQLite权威指南（第2版）》
    * 高难度
        - 《Android的设计与实现 卷1》

## 项目架构
```
├─aars 引用的aar项目
│
├─captures dump内存时生成文件的存放文件夹
│
├─easyim 私信模块
│  └─src
│      ├─androidTest Android测试用例
│      ├─main
│      │  ├─assets
│      │  ├─java
│      │  │  └─com
│      │  │      └─luobo
│      │  │          └─easyim
│      │  │              ├─exception
│      │  │              ├─message   私信协议
│      │  │              ├─receiver  要注册的Android监听器
│      │  │              └─runnable  心跳、发送、接收的Task
│      │  └─res
│      │      └─values
│      └─test Junit测试用例
│
├─luobo 萝卜书摘的主要功能代码
│  ├─bugly 
│  ├─libs 引用的第三方jar包
│  └─src
│      ├─androidTest Android单元测试
│      │
│      ├─test Junit单元测试
│      │
│      ├─main
│      │  ├─assets
│      │  │  ├─arm64-v8a
│      │  │  ├─armeabi-v7a
│      │  │  └─x86
│      │  ├─java
│      │  │  └─com
│      │  │      └─bloomlife
│      │  │          └─luobo
│      │  │              ├─abstracts
│      │  │              │  ├─interfaces
│      │  │              │  └─listeners
│      │  │              ├─activity
│      │  │              │  └─fragment
│      │  │              ├─adapter
│      │  │              ├─app
│      │  │              ├─bus
│      │  │              │  └─event
│      │  │              ├─common
│      │  │              ├─dialog
│      │  │              ├─exception
│      │  │              ├─manager
│      │  │              ├─model
│      │  │              │  ├─cache
│      │  │              │  ├─message
│      │  │              │  └─result
│      │  │              ├─provider
│      │  │              ├─service
│      │  │              ├─util
│      │  │              ├─widget
│      │  │              │  ├─card
│      │  │              │  ├─fits
│      │  │              │  ├─viewpager
│      │  │              │  └─window
│      │  │              └─wxapi
│      │  ├─jniLibs
│      │  │  ├─arm64-v8a
│      │  │  ├─armeabi-v7a
│      │  │  └─x86
│      │  └─res
│      │      ├─anim
│      │      ├─color
│      │      ├─drawable
│      │      ├─drawable-hdpi
│      │      ├─drawable-xhdpi
│      │      ├─drawable-xxhdpi
│      │      ├─layout
│      │      ├─layout-v9
│      │      ├─menu
│      │      ├─mipmap-hdpi
│      │      ├─mipmap-xhdpi
│      │      ├─mipmap-xxhdpi
│      │      ├─mipmap-xxxhdpi
│      │      ├─raw
│      │      ├─values
│      │      ├─values-en
│      │      ├─values-v21
│      │      ├─values-xhdpi
│      │      ├─values-zh
│      │      ├─xml
│      │      └─xml-v25
│      │
│      ├─chuizi 打包锤子渠道APK包时的专有资源，主要是适配锤子手机的重绘图标
│      │  └─res
│      │
│      ├─huawei 打包华为渠道APK包时的专有资源，主要是华为应用商店的闪屏图
│      │  └─res
│      │
│      ├─leshangdian 打包乐商店渠道APK包时的专有资源，主要是乐商店的闪屏图
│      │  └─res
│      │
│      ├─pp 打包PP助手渠道APK包时的专有资源，主要是PP助手的闪屏图
│      │  └─res
│      │
│      ├─sogou 打包搜狗应用商店渠道APK包时的专有资源，主要是搜狗应用商店的闪屏图
│      │  └─res
│      │
│      ├─xiaomi 打包小米应用商店渠道APK包时的专有资源，主要是小米应用商店的闪屏图
│      │  └─res
│      │
│      ├─yingyongbao 打包应用宝渠道APK包时的专有资源，主要是应用宝的闪屏图
│      │  └─res
│      │
│      └─_360 打包360应用商店渠道APK包时的专有资源，主要是360应用商店的闪屏图
│          └─res
│
├─pingpp 第三方支付模块
|
└─zXingProj 二维码识别模块
```
## Android编码风格
本文参考[Hawstein翻译的Google Java编程风格指南](http://www.hawstein.com/posts/google-java-style.html)、[Android开源项目-编码风格规范-Code Style Guidelines for Contributors](http://blog.sina.com.cn/s/blog_48d491300100zwzg.html#use-todo-comments)、[最佳实践之Android代码规范](http://www.androidchina.net/2141.html)

### 目录
[1 命名规范](#user-content-ming-ming-gui-fan)
- [1.1 文件名命名规范](#user-content-wen-jian-ming-ming-ming-gui-fan)
- [1.2 资源ID命名规范](#user-content-zi-yuan-idming-ming-gui-fan)
- [1.3 Drawable文件命名](#user-content-drawablewen-jian-ming-ming)
- [1.4 包命名规范](#user-content-bao-ming-ming-gui-fan)
- [1.5 类名规范](#user-content-lei-ming-gui-fan)
- [1.6 方法名规范](#user-content-fang-fa-ming-gui-fan)
- [1.7 常量名规范](#user-content-chang-liang-ming-gui-fan)
- [1.8 成员变量名规范](#user-content-cheng-yuan-bian-liang-ming-gui-fan)
- [1.9 局部变量名规范](#user-content-ju-bu-bian-liang-ming-gui-fan)

[2 具体结构](https://github.com/yx123lan/wiki/blob/master/README.md#2-具体结构)
- [2.1 Modifiers](https://github.com/yx123lan/wiki/blob/master/README.md#21-modifiers)
- [2.2 大括号问题](https://github.com/yx123lan/wiki/blob/master/README.md#22-大括号问题)
- [2.3 空格问题](https://github.com/yx123lan/wiki/blob/master/README.md#23-空格问题)
- [2.4 枚举类](https://github.com/yx123lan/wiki/blob/master/README.md#24-枚举类)
- [2.5 变量声明](https://github.com/yx123lan/wiki/blob/master/README.md#25-变量声明)
- [2.6 数组](https://github.com/yx123lan/wiki/blob/master/README.md#26-数组)
- [2.7 switch语句](https://github.com/yx123lan/wiki/blob/master/README.md#27-switch语句)
- [2.8 方法参数](https://github.com/yx123lan/wiki/blob/master/README.md#28-方法参数)

[3 编程实践](https://github.com/yx123lan/wiki/blob/master/README.md#3-编程实践)
- [3.1 使用标准的java-annotation](https://github.com/yx123lan/wiki/blob/master/README.md#31-使用标准的java-annotation)
- [3.2 使用TODO注释](https://github.com/yx123lan/wiki/blob/master/README.md#32-使用todo注释)
- [3.3 静态成员](https://github.com/yx123lan/wiki/blob/master/README.md#33-静态成员)
- [3.4 finalizers-禁用](https://github.com/yx123lan/wiki/blob/master/README.md#34-finalizers-禁用)
- [3.5 限制代码行的长度](https://github.com/yx123lan/wiki/blob/master/README.md#35-限制代码行的长度)
- [3.6 编写简短的方法](https://github.com/yx123lan/wiki/blob/master/README.md#36-编写简短的方法)
- [3.7 限制变量的作用范围](https://github.com/yx123lan/wiki/blob/master/README.md#37-限制变量的作用范围)
- [3.8 捕获的异常](https://github.com/yx123lan/wiki/blob/master/README.md#38-捕获的异常)
- [3.9 log的使用](https://github.com/yx123lan/wiki/blob/master/README.md#39-log的使用)

### 1 命名规范
#### *统一使用UTF-8编码，避免乱码问题。*
#### 1.1 文件名命名规范
源文件以其最顶层的类名来命名，大小写敏感，文件扩展名为.java。  
activity的文件：```{名称}Activity``` 例如：```mainActivity.java```

fragment的文件：```{名称}Fragment``` 例如：```tabFragment.java```

dialog的文件：```{名称}Dialog``` 例如：```loginDialog.java```

adapter的文件：```{名称}Adapter``` 例如：```userListAdapter.java```

布局文件全部小写，采用下划线命名法。  
activity layout： ```activity_{名称}``` 例如：```activity_main.xml | activity_shopping.xml```

fragment layout： ```fragment_{名称}``` 例如：```fragment_main.xml | fragment_shopping.xml```

dialog layout： ```dialog_{名称}``` 例如：```dialog_loading.xml```

adapter的子布局： ```item_{名称}``` 例如：```item_order.xml```

widget layout： ```widget_{名称}``` 例如：```widget_shopping_detail.xml```

包含项布局命名： ```include_{名称}``` 例如：```include_head.xml```

#### 1.2 资源ID命名规范
命名模式为：```{view缩写}_{view的逻辑名称}```，如：

顾客管理CRM模块布局 ```LinearLayout``` 的布局id –> ```ll_content```

模块简称为qz的 ```ImageView``` 的布局id –> ```iv_photo```

常见控件View与其缩写对照参考表如下：

| 控件              | 缩写          |
| ----------------- |:-------------:|
| LinearLayout      | ll            |
| Relativelayout    | rl            |
| FrameLayout       | fl            |
| GridLayout        | gl            |
| TextView          | tv            |
| ImageView         | iv            |
| ProgressBar       | proBar        |
| RadioButton       | rb            |
| RecyclerView      | rv            |
| ScrollView        | sv            |
| WebView           | wv            |

#### 1.3 Drawable文件命名

图标命名：```ic_{名称}``` 例如：```ic_app.png```

背景图片命名： ```bg_{名称}```或者```background_{名称}``` 例如：```bg_navbar_highlight_normal.9.png``` | ```background_highlight.xml```  | ```bg_highlight.xml``` 

按钮命名：``` btn_{名称}``` 例如：```btn_login_normal.9.png``` | ```btn_login_normal.xml```

背景选择器Selector文件命名：```{缩写}_{名称}_selector``` 例如：```btn_login_normal_selector.xml```

按钮checkbox图片命名：```checkbox_{名称}``` 例如：```checkbox_cart_true.png```

其他图片命名：```icon_{名称}``` 例如：```icon_blue_circle.png```

#### 1.4 包命名规范
采用反域名命名规则，包名全部小写，连续的单词只是简单地连接起来，不使用下划线，一级包名为com，二级包名为xxx（可以是公司域名或者个人命名），三级包名根据应用进行命名，四级包名为模块名或层级名。
如：````com.zxtcode.activity````

#### 1.5 类名规范
以大驼峰式命名法(UpperCamelCase)风格编写。

每个单词的第一个字母都大写 如:```XmlHttpRequest```

类名通常是名词或名词短语，接口名称有时可能是形容词或形容词短语。现在还没有特定的规则或行之有效的约定来命名注解类型。

测试类的命名以它要测试的类的名称开始，以Test结束。例如，HashTest或HashIntegrationTest。

#### 1.6 方法名规范
以小驼峰式命名法(lowerCamelCase)风格编写。

除了第一个单词，每个单词的第一个字母都大写 如:

```java
public void method(){
}
```

#### 1.7 常量名规范
常量名命名模式为CONSTANT_CASE，全部字母大写，用下划线分隔单词。那，到底什么算是一个常量？

每个常量都是一个静态final字段，但不是所有静态final字段都是常量。在决定一个字段是否是一个常量时， 考虑它是否真的感觉像是一个常量。例如，如果任何一个该实例的观测状态是可变的，则它几乎肯定不会是一个常量。 只是永远不打算改变对象一般是不够的，它要真的一直不变才能将它示为常量。
```java
// Constants
static final int NUMBER = 5;
static final ImmutableList<String> NAMES = ImmutableList.of("Ed", "Ann");
static final Joiner COMMA_JOINER = Joiner.on(',');  // because Joiner is immutable
static final SomeMutableType[] EMPTY_ARRAY = {};
enum SomeEnum { ENUM_CONSTANT }

// Not constants
static String nonFinal = "non-final";
final String nonStatic = "non-static";
static final Set<String> mutableCollection = new HashSet<String>();
static final ImmutableSet<SomeMutableType> mutableElements = ImmutableSet.of(mutable);
static final Logger logger = Logger.getLogger(MyClass.getName());
static final String[] nonEmptyArray = {"these", "can", "change"};
```

#### 1.8 成员变量名规范
以小驼峰式命名法(lowerCamelCase)风格编写。

静态成员变量用s开头。例如：
```java 
private static String sName;
```
除了Model类的私有成员变量以外私有成员变量用m开头。例如：
```java 
private String mName;
```
Model类的私有成员变量不加前缀。例如：
```java 
private String name;
```

#### 1.9 局部变量名规范
以小驼峰式命名法(lowerCamelCase)风格编写。

除了第一个单词，每个单词的第一个字母都大写 如:
```java
String name = "a";
int id = 1;
```
### 2 具体结构

#### 2.1 Modifiers
类和成员的modifiers如果存在，则按Java语言规范中推荐的顺序出现。
```java
public protected private abstract static final transient volatile synchronized native strictfp
```

#### 2.2 大括号问题
将大括号与起始语句放在同一行
```java
if (hasSomething()) {
 
} else {
 
}
```
我们需要用大括号来包裹条件语句块。不过也有例外，如果整个条件语句块（条件和语句本身）都能容纳在一行内，也可以（但不是必须）把它们放入同一行中。也就是说，这是合法的：
```java
if (condition) body();
```
不要这样写：
```java
if (isEmpty())
    empty... 
else
    something...
```
或
```java
if (hasSomething())
    body();  // bad!
```

#### 2.3 空格问题
if else | while | 运算符两端 等后面需用空格隔开。例如：

规范的编写方式：
```java
if (hasSomething()) {
 
} else {
 
}
 
for (int i = 0; i < 10; i++) {
 
}
```

不规范的编写方式：
```java
if(hasSomething()){
 
}else{
 
}
 
for(int i=0; i<10;i++){
 
}
```

#### 2.4 枚举类
枚举常量间用逗号隔开，换行可选。

没有方法和文档的枚举类可写成数组初始化的格式：
```java
private enum Suit { CLUBS, HEARTS, SPADES, DIAMONDS }
```
由于枚举类也是一个类，因此所有适用于其它类的格式规则也适用于枚举类。

#### 2.5 变量声明
- 每次只声明一个变量。不要使用组合声明，比如int a, b;。
- 需要时才声明，并尽快进行初始化。不要在一个代码块的开头把局部变量一次性都声明了(这是c语言的做法)，而是在第一次需要使用它时才声明。 局部变量在声明时最好就进行初始化，或者声明后尽快进行初始化。

#### 2.6 数组
- 数组初始化可以写成块状结构，比如，下面的写法都是OK的：
```java
new int[] {
  0, 1, 2, 3 
}

new int[] {
  0,
  1,
  2,
  3
}

new int[] {
  0, 1,
  2, 3
}

new int[]{0, 1, 2, 3}
```
- 非C风格的数组声明。中括号是类型的一部分：String[] args， 而非String args[]。

#### 2.7 switch语句
**术语说明：**switch块的大括号内是一个或多个语句组。每个语句组包含一个或多个switch标签(case FOO:或default:)，后面跟着一条或多条语句。
- 缩进。与其它块状结构一致，switch块中的内容缩进为2个空格。每个switch标签后新起一行，再缩进2个空格，写下一条或多条语句。
- Fall-through：注释
在一个switch块内，每个语句组要么通过break, continue, return或抛出异常来终止，要么通过一条注释来说明程序将继续执行到下一个语句组， 任何能表达这个意思的注释都是OK的(典型的是用// fall through)。这个特殊的注释并不需要在最后一个语句组(一般是default)中出现。示例：
```java
switch (input) {
  case 1:
  case 2:
    prepareOneOrTwo();
    // fall through
  case 3:
    handleOneTwoOrThree();
    break;
  default:
    handleLargeNumber(input);
}
```
-  default的情况要写出来。每个switch语句都包含一个default语句组，即使它什么代码也不包含。

#### 2.8 方法参数
1. 当方法参数数量过多时，需进行换行处理。
2. 尽量不要让方法参数超过五个，超过五个以上可以考虑用一个类来封装。
3. 除非只有一个参数，尽量不要使用boolean作为方法参数
4. 如果需要传的参数是Android的资源文件ID，那么需要加上注解。
Drawable使用```@DrawableRes```，Color使用```@ColorRes```，Dimension使用```@DimenRes```，String使用```@StringRes```。

### 3 编程实践
#### 3.1 使用标准的Java Annotation
Annotation应该位于Java语言元素的其它修饰符之前。 简单的marker annotation（@Override等）可以和语言元素放在同一行。 如果存在多个annotation，或者annotation是参数化的，则应按字母顺序各占一行来列出。

对于Java 内建的三种annotation，Android标准的实现如下
- @Deprecated：只要某个语言元素已不再建议使用了，就必须使用@Deprecated annotation。如果使用了@Deprecated annotation，则必须同时进行@deprecated Javadoc标记，并且给出一个替代的实现方式。  
此外请记住，被@Deprecated的方法仍然是能正常执行的。  如果看到以前的代码带有@deprecated Javadoc标记，也请加上@Deprecated annotation。
- @Override:只要某个方法覆盖了已过时的或继承自超类的方法，就必须使用@Override annotation。  
例如，如果方法使用了@inheritdocs Javadoc标记，且继承自超类（而不是interface），则必须同时用@Override标明覆盖了父类方法。
- @SuppressWarnings：@SuppressWarnings annotation仅用于无法消除编译警告的场合。   如果警告确实经过测试“不可能消除”，则必须使用@SuppressWarnings annotation，以确保所有的警告都能真实反映代码中的问题。  当需要使用@SuppressWarnings annotation时，必须在前面加上TODO注释行，用于解释“不可能消除”警告的条件。通常是标明某个令人讨厌的类用到了某个拙劣的接口。比如：
```java
// TODO: The third-party class com.third.useful.Utility.rotate() needs generics
@SuppressWarnings("generic-cast")
List<String> blix = Utility.rotate(blax);
```
如果需要使用@SuppressWarnings annotation，应该重新组织一下代码，把需要应用annotation的语言元素独立出来。

#### 3.2 使用TODO注释
对那些临时性的、短期的、够棒但不完美的代码，请使用TODO注释。
TODO注释应该包含全部大写的TODO，后跟一个冒号：
```java
// TODO: Remove this code after the UrlTable2 has been checked in.
```
和
```java
// TODO: Change this to use a flag instead of a constant.
```
如果TODO注释是“将来要做某事”的格式，则请确保包含一个很明确的日期（“在2005年11月会修正”），或是一个很明确的事件（“在所有代码整合人员理解了V7协议之后删除本段代码”）。

#### 3.3 静态成员
使用类名调用静态的类成员，而不是具体某个对象或表达式。
```java
Foo aFoo = ...;
Foo.aStaticMethod(); // good
aFoo.aStaticMethod(); // bad
somethingThatYieldsAFoo().aStaticMethod(); // very bad
```

#### 3.4 Finalizers: 禁用
极少会去重写Object.finalize。
Tip：不要使用finalize。如果你非要使用它，请先仔细阅读和理解Effective Java 第7条款：“Avoid Finalizers”，然后不要使用它。

#### 3.5 限制代码行的长度
每行代码的长度应该不超过100个字符。

有关本规则的讨论有很多，最后的结论还是最多不超过100个字符。

例外：如果注释行包含了超过100个字符的命令示例或者URL文字，为了便于剪切和复制，其长度可以超过100个字符。

例外：import行可以超过限制，因为很少有人会去阅读它。这也简化了编程工具的写入操作。

#### 3.6 编写简短的方法
为了把规模控制在合理范围内，方法应该保持简短和重点突出。不过，有时较长的方法也是合适的，所以对方法的代码长度并没有硬性的限制。如果方法代码超过了40行，就该考虑是否可以在不损害程序结构的前提下进行分拆。

#### 3.7 限制变量的作用范围
局部变量的作用范围应该是限制为最小的（Effective Java第29条）。使用局部变量，可以增加代码的可读性和可维护性，并且降低发生错误的可能性。每个变量都应该在最小范围的代码块中进行声明，该代码块的大小只要能够包含所有对该变量的使用即可。

应该在第一次用到局部变量的地方对其进行声明。几乎所有局部变量声明都应该进行初始化。如果还缺少足够的信息来正确地初始化变量，那就应该推迟声明，直至可以初始化为止。

本规则存在一个例外，就是涉及try-catch语句的情况。如果变量是用方法的返回值来初始化的，而该方法可能会抛出一个checked异常，那么必须在try块中进行变量声明。如果需在try块之外使用该变量，那它就必须在try块之前就进行声明了，这时它是不可能进行正确的初始化的。
```java
// Instantiate class cl, which represents some sort of Set
Set s = null;
try {
    s = (Set) cl.newInstance();
} catch(IllegalAccessException e) {
    throw new IllegalArgumentException(cl + " not accessible");
} catch(InstantiationException e) {
    throw new IllegalArgumentException(cl + " not instantiable");
}
// Exercise the set
s.addAll(Arrays.asList(args));
````
但即便是这种情况也是可以避免的，把try-catch 块封装在一个方法内即可：
```java
Set createSet(Class cl) {
    // Instantiate class cl, which represents some sort of Set
    try {
        return (Set) cl.newInstance();
    } catch(IllegalAccessException e) {
        throw new IllegalArgumentException(cl + " not accessible");
    } catch(InstantiationException e) {
        throw new IllegalArgumentException(cl + " not instantiable");
    }
}
...

// Exercise the set
Set s = createSet(cl);
s.addAll(Arrays.asList(args));
```

除非理由十分充分，否则循环变量都应该在for语句内进行声明，：
```java
for (int i = 0; i n; i++) {
    doSomething(i);
}
```
和
```java
for (Iterator i = c.iterator(); i.hasNext(); ) {
    doSomethingElse(i.next());
}
```

#### 3.8 捕获的异常
有时，完全忽略异常是非常诱人的，比如：
```java
void setServerPort(String value) {
    try {
        serverPort = Integer.parseInt(value);
    } catch (NumberFormatException e) { }
}
```
绝对不要这么做。也许你会认为：你的代码永远不会碰到这种出错的情况，或者处理异常并不重要，可类似上述忽略异常的代码将会在代码中埋下一颗地雷，说不定哪天它就会炸到某个人了。你必须在代码中以某种规矩来处理所有的异常。根据情况的不同，处理的方式也会不一样。
无论何时，空的Java中你无法逃离这种恐惧感。 -James Gosling
可接受的替代方案包括（按照推荐顺序）：
- 向方法的调用者抛出异常。
```java
void setServerPort(String value) throws NumberFormatException {
    serverPort = Integer.parseInt(value);
}
```
- 根据抽象级别抛出新的异常。
```java
void setServerPort(String value) throws ConfigurationException {
    try {
        serverPort = Integer.parseInt(value);
    } catch (NumberFormatException e) {
        throw new ConfigurationException("Port " + value + " is not valid.");
    }
}
```
- 语句块中替换为合适的值。
``` java
void setServerPort(String value) {
    try {
        serverPort = Integer.parseInt(value);
    } catch (NumberFormatException e) {
        serverPort = 80;  // default port for server
    }
}
```
- RuntimeException。这种做法比较危险：只有确信发生该错误时最合适的做法就是崩溃，才会这么做。请记住，最初的异常是传递给构造方法的RuntimeException。如果代码必须在Java 1.3版本下编译，需要忽略该异常。
```java
void setServerPort(String value) {
    try {
        serverPort = Integer.parseInt(value);
    } catch (NumberFormatException e) {
        throw new RuntimeException("port " + value " is invalid, ", e);
    }
}
```

- 最后一招：如果确信忽略异常比较合适，那就忽略吧，但必须把理想的原因注释出来：
```java
try {
  int i = Integer.parseInt(response);
  return handleNumericResponse(i);
} catch (NumberFormatException ok) {
  // it's not numeric; that's fine, just continue
}
return handleTextResponse(response);
```

例外：在测试中，如果一个捕获的异常被命名为expected，则它可以被不加注释地忽略。下面是一种非常常见的情形，用以确保所测试的方法会抛出一个期望中的异常， 因此在这里就没有必要加注释。
```java
try {
    emptyStack.pop();
    fail();
} catch (NoSuchElementException expected) {
}
```
**不要捕获顶级的Exception** 有时在捕获Exception时偷懒也是很吸引人的，类似如下的处理方式：
```java
try {
    someComplicatedIOFunction();        // may throw IOException
    someComplicatedParsingFunction();   // may throw ParsingException
    someComplicatedSecurityFunction();  // may throw SecurityException
    // phew, made it all the way
} catch (Exception e) {                 // I'll just catch all exceptions
    handleError();                      // with one generic handler!
}
```
不要这么做。绝大部分情况下，捕获顶级的RuntimeException被卷入到应用程序级的错误处理中来。这会让代码运行的错误变得模糊不清。这意味着，假如别人在你调用的代码中加入了新的异常，编译器将无法帮助你识别出各种不同的错误类型。绝大部分情况下，无论如何你都不应该用同一种方式来处理各种不同类型的异常。  

本规则也有极少数例外情况：期望捕获所有类型错误的特定的测试代码和顶层代码（为了阻止这些错误在用户界面上显示出来，或者保持批量工作的运行。这种情况下可以捕获顶级的Throwable并进行相应的错误处理。在开始之前，你应该非常仔细地考虑一下，并在注释中解释清楚为什么这么做是安全的。  
比捕获顶级Exception更好的方案：  

1. catch 语句块。这样可能会有点别扭，但总比捕获所有语句块中重复执行大量的代码。  
2. IO从解析内容的代码中分离出来，根据各自的情况进行单独的错误处理。  
3. 再次抛出异常。很多时候在你这个级别根本就没必要捕获这个异常，只要让方法抛出该异常即可。  

请记住：异常是你的朋友！当编译器指出你没有捕获某个异常时，请不要皱眉头。而应该微笑：编译器帮助你找到了代码中的运行时（runtime）问题。

#### 3.9 Log的使用
记录日志会对性能产生显著的负面影响。如果日志内容不够简炼的话，很快会丧失可用性。日志功能支持五种不同的级别。以下列出了各个级别及其使用场合和方式。

- ERROR: 该级别日志应该在致命错误发生时使用，也就是说，错误的后果能被用户看到，但是不明确删除部分数据、卸装程序、清除数据区或重新刷机（或更糟糕）就无法恢复。该级别总是记录日志。需要记录ERROR级别日志的事件一般都应该向统计信息收集（statistics-gathering ）服务器报告。

- WARNING: 该级别日志应该用于那些重大的、意外的事件，也就是说，错误的后果能被用户看到，但是不采取明确的动作可能就无法无损恢复，从等待或重启应用开始，直至重新下载新版程序或重启设备。该级别总是记录日志。需记录WARNING级别日志的事件也可以考虑向统计信息收集服务器报告。

- INFORMATIVE: 该级别的日志应该用于记录大部分人都会感兴趣的事件，也就是说，如果检测到事件的影响面可能很广，但不一定是错误。应该只有那些拥有本区域内最高级别身份认证的模块才能记录这些日志（为了避免级别不足的模块重复记录日志）。该级别总是记录日志。

- DEBUG: 该级别的日志应该用于进一步记录有关调查、调试意外现象的设备事件。应该只记录那些有关控件运行所必需的信息。如果debug日志占用了太多的日志空间，那就应该使用详细级别日志（verbose）才更为合适。

即使是发行版本（release build），该级别也会被记录，并且需用if (LOCAL_LOG)或if (LOCAL_LOGD)语句块包裹，这里的LOCAL_LOG[D]在你的类或子控件中定义。这样就能够一次性关闭所有的调试日志。因此在if (LOCAL_LOG)语句块中不允许存在逻辑判断语句。所有日志所需的文字组织工作也应在if (LOCAL_LOG)语句块内完成。如果对记录日志的调用会导致在if (LOCAL_LOG)语句块之外完成文字组织工作，那该调用就必须控制在一个方法内完成。

还存在一些代码仍然在使用if (localLOGV)。这也是可以接受的，虽然名称不是标准的。

- VERBOSE: 该级别日志应用于所有其余的事件。该级别仅会在调试版本（debug build）下记录日志，并且需用if (LOCAL_LOGV)语句块（或等效语句）包裹，这样该部分代码默认就不会编译进发行版本中去了。所有构建日志文字的代码将会在发行版本中剥离出去，并且需包含在if (LOCAL_LOGV)语句块中。

*注意：*

- *除了VERBOSE级别外，在同一个模块中同一个错误应该尽可能只报告一次：在同一个模块内的一系列层层嵌套的函数调用中，只有最内层的函数才返回错误；并且只有能为解决问题提供明显帮助的时候，同一模块中的调用方才写入一些日志。*

- *除了VERBOSE级别外，在一系列嵌套的模块中，当较低级别的模块对来自较高级别模块的非法数据进行检测时，应该只把检测情况记录在DEBUG日志中，并且只记录那些调用者无法获取的信息。特别是不需要记录已经抛出异常的情况（异常中应该包含了全部有价值的信息），也不必记录那些只包含错误代码的信息。当应用程序与系统框架间进行交互时，这一点尤为重要。系统框架已能正确处理的第三方应用程序，也不应该记录大于DEBUG级别的日志。仅当一个模块或应用程序检测到自身或来自更低级别模块的错误时，才应该记录INFORMATIVE及以上级别的日志。*

- *如果一个通常要记录日志的事件可能会多次发生，则采取一些频次限制措施或许是个好主意，以防日志被很多重复（或类似）的信息给撑爆了。*

- *网络连接的丢失可被视为常见现象，也是完全可以预见的，不应该无缘无故就记录进日志。影响范围限于应用程序内部的网络中断应该记录在DEBUG或VERBOSE级别的日志中（根据影响的严重程度及意外程度，再来确定是否在发行版本中也记录日志）。*

- *有权访问的文件系统或第三方应用程序发起的系统空间满，应该记录大于INFORMATIVE级别的日志。*

- *来自任何未授信源的非法数据（包括共享存储上的任何文件，或来自任何网络连接的数据）可被视为可预见的，如果检测到非法数据也不应该记录大于DEBUG级别的日志（即使记录也应尽可能少）。*

- *请记住，对字符串使用+操作符时，会在后台以默认大小（16个字符）缓冲区创建一个StringBuilder对象，并且可能还会创建一些其它的临时String对象。换句话说，显式创建StringBuilders对象的代价并不会比用'+'操作符更高（事实上效率还将会提高很多）。还要记住，即使不会再去读取这些日志，调用Log.v()的代码也将编译进发行版中并获得执行，包括创建字符串的代码。*

- *所有要被人阅读并存在于发行版本中的日志，都应该简洁明了、没有秘密、容易理解。这里包括所有DEBUG以上级别的日志。*

- *只要有可能，日志就应该一句一行。行长最好不超过80或100个字符，尽可能避免超过130或160个字符（包括标识符）的行。*

- *报告成功的日志记录绝不应该出现在大于VERBOSE级别的日志中。*

- *用于诊断难以重现事件的临时日志应该限于DEBUG或VERBOSE级别，并且应该用if语句块包裹，以便在编译时能够一次全部关闭。*

- *小心日志会泄漏隐私。应该避免将私人信息记入日志，受保护的内容肯定也不允许记录。这在编写系统框架级代码时尤为重要，因为很难预知哪些是私人信息和受保护信息。*

- *绝对不要使用System.out.println() （或本地代码中的printf()）。System.out 和 System.err会重定向到/dev/null，因此print语句不会产生任何可见的效果。可是，这些调用中的所有字符串创建工作都仍然会执行。*

- *日志的黄金法则是：你的日志记录不会导致其它日志的缓冲区溢出，正如其他人的日志也不会让你的溢出一样。*
