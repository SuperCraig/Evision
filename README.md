<div align=center><img width="100" height="100" src="https://github.com/AngelaViVi/Evision/blob/master/src/EvisionLegacy/res/Evision.ico"/></div>

<div align=center>Evision 双目视觉系统</div>

Feature:
=========
1. 双目测距<br>
2. 标定,畸变校正<br>
3. 三维点云获取<br>
4. 关于双目的中文资料重复度太高,希望各位后来者能够析取前人精华,摒弃前人的糟粕,多多自行探索,不要抄来抄去<br>
5. 关于程序使用方面的问题,可以联系邮件jiafeng5513@outlook.com<br>
6. 有关课程设计和毕业论文(Windows程序开发,机器视觉,深度学习,图像处理)的相关事宜也可以联系作者.<br>

Comming soon
===

1. 测距部分的优化.<br>
2. 录制新的视频.<br>
3. 发布release版本.<br>
4. 链接持续集成工具.<br> 
5. 更新博客:<br>
> 1. 极线约束.<br>
> 2. 标定方法原理.<br>
> 3. 匹配方法原理,参数意义以及调整参数的方法.<br>
> 4. 测距算法解释.<br>
> 5. Visual Studio编译期脚本的使用.<br>
> 6. QtDesigner插件编写.<br>

#### 安装指南

1. [Qt安装指南](https://github.com/AngelaViVi/Evision/blob/master/doc/Qt_Install.md)<br>
2. [VS2017安装指南](https://github.com/AngelaViVi/Evision/blob/master/doc/VS2017_Install.md)<br>
3. [VS2017-Qt配置指南](https://github.com/AngelaViVi/Evision/blob/master/doc/qt_vs_config.md)<br>

build
===
#### 路径说明
1. `data`文件夹存储测试用例<br>
2. `package`文件夹存储项目所需的依赖<br>
3. `scripts`文件夹存储编译脚本,由于使用了VisualStudio宏,这些脚本不能直接运行.<br>
4. `src`文件夹中存放工程目录和解决方案文件.<br>
#### 使用须知
1. 为了对新手友好,写的比较详细(啰嗦),请谅解.如果您并不是一个写过很多相关程序的用户,请仔细阅读.<br>
1. 使用该项目需要准备Visual Studio 2017,Qt 5.11.1.如果您没有这两个IDE的使用经验,请务必按照上面提供的安装教程进行安装.<br>
2. 本项目已经将所需的依赖内置好,如果您对Visual Studio并不熟悉,请不要修改项目属性.<br>
3. 请不要按照其他教程(形如"OpenCV和VS2017环境搭建"之类)中的步骤修改本项目的配置.<br>
4. 项目中带有很多脚本,在不清楚这些脚本的作用的情况下,请不要修改删除或者随意执行.<br>
#### 工程说明
本项目有两个解决方案,用VS2017打开`src/Evision.sln`,你将看到其中含有使用7个工程:<br>
![image](https://github.com/AngelaViVi/Evision/blob/master/doc/sln_and_projs.png)
1. calibration是标定的sample,是一个控制台程序.<br>
2. imagelist_creator是文件序列化sample,控制台程序.<br>
3. stereo_match是立体匹配sample,控制台程序.<br>
4. EvisionLegacy是MFC版本的Evision主程序,GUI程序<br>
5. CustomGraphicsView是自定义QtDesigner插件.<br>
6. Evision是Qt版的Evision主程序,GUI.<br>
用VS2017打开`src/CvLib.sln`,你将会看到两个工程:<br>
![image](https://github.com/AngelaViVi/Evision/blob/CvLib/doc/cvlib_sln_proj.png)
1. CvLabMain是用WPF框架写的.<br>
2. CvLabSandbox是用WinFrom写的.<br>

#### MFC(EvisionLegacy)
1. OpenCV版本:2.4.13,解决方案文件夹已经内置了一个OpenCV<br>
2. VS2017,兼容msvc15-2017,V140.v141工具集<br>
3. 需要安装Windows 10 SDK<br>
4. 运行exe时若提示缺少某些dll,只需在OpenCV中找到相应的dll放在exe旁边就可以,或者将dll的路径加入到环境变量.<br>
5. 如果您没有修改该工程的任何地方,使用的正确版本的VS,但是却发现无法通过编译,一定是您的开发机环境有问题或操作问题.<br>
6. 本人保证,程序是能够通过编译并正常运行的,这不仅仅是在我自己的开发机上验证过,也在很多使用过程序的用户的电脑上验证过.<br>
7. 为了能正常编译并运行MFC程序,您的电脑需要满足以下要求:<br>
> 1. 至少是window7系统,推荐使用windows10<br>
> 2. VS要安装如下组件:使用C++的桌面开发,windows 10 SDK (10.0.17134.0),Windows 通用C运行时,用于x86和x64的Visual C++ ATL,用于x86和x64的Visual C++ MFC,Visual C++核心功能,VC++2017版本15.8 v14.15最新v141工具集,Windows 通用CRT SDK,对C++的Windows XP支持.<br>
> 3. 如果您没有安装上述组件,将会在编译运行中遇到不可预知的错误,若发生这些情况,请检查您的VS2017是否安装了上述组件.<br>
8. 由于MFC程序年代久远,已经停止维护并且已经失去了可维护性,在这段时间内,OpenCV也已经发生了巨大的变化,本人强烈建议不要再使用MFC版本,更不要尝试修改或者扩展MFC的程序.目前,基于Qt的新程序已经基本开发完毕,届时MFC版本将会删除,项目也将会改名.<br>

#### Qt(Evision)
1. Qt版本:Qt 5.11.1<br>
2. Vs版本:2017<br>
3. Opencv:3.4.1,程序自带依赖,不需要下载opencv,不要随意修改成其他版本,不保证能用.<br>
4. 带有编译脚本,可以自动将程序所需的dll复制到exe旁边,不需要设置环境变量.<br>
5. 下载使用时,请不要修改这个项目的VS项目设置,我已经考虑了移植问题,该项目的工程文件(vcproj)比较复杂,如果您不是很熟悉VS的操作,请务必不要修改.<br>

#### CvLabMain和CvLabSandbox
1. features
>>1. Docking风格MDI界面<br>
>>2. 使用MVP设计模式,交互基于双向数据绑定<br>
2. build
>>1. VS2017<br>
>>2. .NET 4.6.1<br>
>>3. 依赖使用Nuget下载<br>
3. Package
>>1.AForge.2.2.5<br>
>>2.AForge.Video.2.2.5<br>
>>3.AForge.Video.DirectShow.2.2.5<br>
>>4.EMGU.CV.3.3.0.2824<br>
>>5.cskin.16.1.14.3<br>
>>6.WeifenLuo.WinFormsUI.Docking.2.1.0<br>
>>7.ZedGraph.5.1.5<br>

其他
===
1. 这个程序将会开始更新,由于主要作者比较忙,更新时间不确定<br>
2. 这是本人编程路上第一个稍微像样的程序,在编写中得到了许多前辈的帮助,无法一一列举.当时寻找靠谱的教程和参考价值高的代码异常费劲,这个经历让我决定,以后我写的所有代码尽量都开放,如果有应用价值,我也会尽量写博客,编程是一件需要大家互相帮助的事情,尤其是对于初学者,他们更需要社区环境的关爱.<br>
3. 感谢大家的关注,新版本的程序已经接近完成,届时该repo将会改名,相关的博客和视频连接都会同步更新,博客会不定期发布最新的算法的相关文章,欢迎大家继续关注,等一切准备妥当,将会放链接.<br>
4. 作者所用的设备:![image](https://github.com/AngelaViVi/Evision/blob/master/doc/device.png)<br>