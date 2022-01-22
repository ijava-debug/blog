---
layout: post
title: 计算机组成原理(1)
---
{: .note .info}  
本文主要介绍计算机的层次结构及计算机的基本组成

## 计算机的层次结构
如图所示：  

<div align=center><img src="https://raw.githubusercontent.com/ijava-debug/pic/main/%E5%A4%9A%E7%BA%A7%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84%E7%9A%84%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%B3%BB%E7%BB%9F.png"></div> 


早期的计算机只有机器语言（用0、1代码表示的语言），用户只能使用二进制代码来编写程序。使用机器语言的好处是编写好的程序可以直接在机器上运行，但是这要求程序员对他们所使用的计算机硬件及指令系统非常熟悉，编写程序难度很大，操作过程中也容易出错。  

20世纪50年代开始出现符号式的程序设计语言，即汇编语言。它用符号ADD、SUB、MUL、DIV等分别表示加、减、乘、除等操作，并用符号表示指令或数据在存储单元上的地址，使程序员可以不再使用复杂又容易出错的二进制代码来编写程序。但实际上没有任何一种机器能够识别汇编语言，即汇编语言是不能直接在机器上运行，必须先将汇编语言翻译成机器语言，然后才能被机器接受并自动运行。汇编语言翻译成机器语言的工作是由机器的系统软件程序完成的，完成这一工作的软件程序成为汇编语言机器（并不是实际的机器，而是虚拟机器），执行机器语言的是真实的机器（机器语言机器）。实际上机器语言机器和汇编语言机器中间还有一层操作系统机器，它是由操作系统软件构成的，起到控制并管理计算机系统全部硬件和软件资源的作用。

汇编语言的出现使用户编程更方便了，但本质上汇编语言仍是一种面向实际机器的语言，仍然要求用户对实际机器的硬件组成及指令系统非常熟悉；另一方面，汇编语言摆脱不了实际机器的指令的系统，没有通用性，每台机器必须有一种与之相对应的指令系统，这就要求程序员必须掌握不同机器的指令系统，不利于计算机的发展和应用。

因此20世纪60年代出现了各种面向问题的高级语言，高级语言对问题的描述比较符号人类的习惯，并且具有很强的通用性。高级语言使得程序员可以不用了解实际机器的硬件组成及指令系统，只要掌握了高级语言的语法和语义即可用它来编写程序。将高级语言翻译成汇编语言的程序成为翻译程序，翻译程序有两种，一种是编译程序，将所有代码翻译成机器语言再输入到机器语言机器，只有源代码不改变就不用重新翻译；一种是解释程序，将一条代码翻译成机器语言并执行后接着翻译下一条代码，即是是重复的代码也要重新翻译。

实际机器M1向上延伸发展出了各种虚拟机器，同理M1内部也可以向下延伸发展微程序机器M0。M0是将M1的一条指令拆分成一组微指令，构成一个微程序。

## 计算机的基本组成

### 冯诺伊曼计算机结构框图：    

1945年冯诺伊曼提出了"存储程序"的概念，以此为基础的各类计算机成为冯诺伊曼计算机。  

<div align=center><img src="https://raw.githubusercontent.com/ijava-debug/pic/main/%E5%86%AF%E8%AF%BA%E4%BC%8A%E6%9B%BC%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BB%93%E6%9E%84%E6%A1%86%E5%9B%BE.png"></div> 



 冯诺伊曼计算机的特点：

+ 计算机由控制器、运算器、存储器、输入设备、输出设备五大部分组成
+ 指令和数据已通等地位存放在存储器中，并可按地址寻访
+ 指令和数据均用二进制表示
+ 指令由操作码和和地址码组成，操作码用来表示操作的性质（机器执行的各种操作），地址码用来表示操作数在内存中的位置
+ 指令在存储器中按顺序存放。通常，指令是按顺序执行的，在特定条件下可根据运算结果或设定的条件改变执行的顺序
+ 运算器为中心，输入输出设备与存储器的数据传送通过运算器完成



### 以存储器为中心的计算机结构框图：

冯诺伊曼计算机是以运算器为中心的，现代计算机已演化成以存储器为中心。  

![](https://raw.githubusercontent.com/ijava-debug/pic/main/%E4%BB%A5%E5%AD%98%E5%82%A8%E5%99%A8%E4%B8%BA%E4%B8%AD%E5%BF%83%E7%9A%84%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BB%93%E6%9E%84%E6%A1%86%E5%9B%BE.png)  

各部件的功能如下：  

+ 运算器用来完成算术运算和逻辑运算，并将运算的中间结果暂存在运算器内
+ 存储器用来存放数据和程序
+ 控制器用来控制、指挥程序和数据的输入、运行以及处理运算结果
+ 输入设备用来将人们熟悉的信息形式转换为机器能够识别的信息形式，如键盘、鼠标等
+ 输出设备用来将机器运算结果转换为人们熟悉的信息形式，如打印机、显示器等

### 现代计算机的组成框图：

由于运算器和控制器在逻辑关系和电路结构上关系十分紧密，通常把它们合起来统称为中央处理器（Central Processing Unit,CPU）。把输入输出设置简称为I/O设备（Input/Output Equitment）。这样现代计算机可认为由三大部分组成：CPU、I/O设备、主存储器（Main Memory,MM），如下图所示。CPU和主存储器和起来称为主机，I/O设备称为外部设备。

<div align=center><img src="https://raw.githubusercontent.com/ijava-debug/pic/main/%E7%8E%B0%E4%BB%A3%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%9A%84%E7%BB%84%E6%88%90%E6%A1%86%E5%9B%BE.png"></div>

### 细化的计算机结构框图：

<div align=center><img src="https://raw.githubusercontent.com/ijava-debug/pic/main/%E7%BB%86%E5%8C%96%E7%9A%84%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BB%84%E6%88%90%E6%A1%86%E5%9B%BE.png"></div>







<!---
语法高亮

--->

{% highlight java linenos %}

# some ruby code
int a = 10;
public void showMesg{
	printf("hello world");
}

**if**(msg.shareChannel == NT_SHARE_TYPE_TWITTER) {

​    NTLog(@"msg.shareChannel == NT_SHARE_TYPE_TWITTER");

​    **if**(msg.shareBitmap == **nil** || [msg.text isEqualToString:@""] || [msg.link isEqualToString:@""]){

​      NTLog(@"分享错误shareBitmap text link空");

​      **return**;

​    }

​    [SDKTxwyPassport twitterFeed:msg.text image:msg.shareBitmap link:[NSURL URLWithString:msg.link] completion:^(**BOOL** success) {

​      **if** (success) {

​        NTLog(@"twitterFeed分享成功");

​        [NtNotificationHelper postNotificationName:NT_NOTIFICATION_FINSIH_SHARE userInfo:@{@"result":@(**YES**)}];

​      }

​      **else** {

​        NTLog(@"twitterFeed分享failed");

​        [NtNotificationHelper postNotificationName:NT_NOTIFICATION_FINSIH_SHARE userInfo:@{@"result":@(**NO**)}];

​      }

​    }];

  }

  **if**(msg.shareChannel == NT_SHARE_TYPE_KAKAO) {

​    NTLog(@"msg.shareChannel == NT_SHARE_TYPE_KAKAO");

​    **if**(msg.shareBitmap == **nil**){

​      NTLog(@"分享错误shareBitmap空");

​      **return**;

​    }

​    **if**([msg.text isEqualToString:@""]){

​      NTLog(@" text空 KakaoTalkFeed");

​      **if**([msg.link isEqualToString:@""]){

​        NTLog(@"分享错误 link空");

​        **return**;

​      }

​      [SDKTxwyPassport KakaoTalkFeed:[NSURL URLWithString:msg.link] title:msg.title description:msg.desc image:msg.shareBitmap completion:^(**BOOL** success) {

​        **if** (success) {

​          NTLog(@"KakaoTalkFeed分享成功");

​          [NtNotificationHelper postNotificationName:NT_NOTIFICATION_FINSIH_SHARE userInfo:@{@"result":@(**YES**)}];

​        }

​        **else** {

​          NTLog(@"KakaoTalkFeed分享失败");

​          [NtNotificationHelper postNotificationName:NT_NOTIFICATION_FINSIH_SHARE userInfo:@{@"result":@(**NO**)}];

​        }

​      }];

​      **return**;

​    }

{% endhighlight %}
