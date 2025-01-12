## 代码审查仓库
> 如果本项目对你有帮助，欢迎在[:link:Github](https://github.com/zkytech/iOS14-widgets-for-scriptable)点个star表示支持。
> 
> 联系邮箱：zhangkunyuan@hotmail.com ，PR请提交到[:link:Github](https://github.com/zkytech/iOS14-widgets-for-scriptable) 

## 紧急通知：2023年4月4日，官方调整了API接口认证方式，导致旧版脚本无法正常使用，脚本已经完成更新适配，需要获取新的`Authorization`参数，具体方法请看下面文档。
# iOS 14小组件
<!-- vscode-markdown-toc -->
- [iOS 14小组件](#ios-14小组件)
  - [使用方法](#使用方法)
    - [安装scriptable](#安装scriptable)
    - [安装脚本](#安装脚本)
    - [使用](#使用)
  - [ 小组件：bilibili最近更新番剧列表](#-小组件bilibili最近更新番剧列表)
    - [效果预览](#效果预览)
    - [安装](#安装)
    - [参数](#参数)
  - [小组件：LOL近期赛事列表](#小组件lol近期赛事列表)
    - [效果预览](#效果预览-1)
    - [安装](#安装-1)
  - [小组件：深蓝SL03车辆状态](#小组件深蓝sl03车辆状态)
    - [效果预览](#效果预览-2)
    - [安装](#安装-2)
    - [参数](#参数-1)
      - [`Authorization`获取方法](#Authorization获取方法)
        - [速通版本](#速通版本)
        - [详细版本](#详细版本)
    - [主题设置、自定义车辆图片、LOGO、型号文本...](#主题设置自定义车辆图片logo型号文本)

<!-- vscode-markdown-toc-config
	numbering=false
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->
## 使用方法
### 安装scriptable
安装App Store中的[:link:Scriptable](https://apps.apple.com/cn/app/scriptable/id1405459188)
<!-- > 这里建议安装测试版，因为测试版支持更多特性，且我的脚本一般是以测试版为基础编写的。 -->

### 安装脚本

下方各组件的章节内有对应脚本的安装链接，点击下载后用`Scriptable APP`打开。选择`Add to my scripts`即可。


![](./preview/安装脚本.jpg)

### 使用

1. 安装scriptable后会自动创建几个Demo脚本，其中有一个脚本是`Random Scriptable API`，先点击运行一次这个脚本。

2. 在桌面创建小组件 选择 `scriptable`

3. 编辑 小组件，点击`选取 script` 并选择前面导入的脚本。


## <a name='2-bilibili最近更新番剧列表'></a> 小组件：bilibili最近更新番剧列表

### <a name='2.1-效果预览'></a>效果预览

![](./preview/bilibili预览.JPEG)

### <a name='2.2-安装'></a>安装

下载[:link:安装脚本](https://github.com/Max-Sum/iOS14-widgets-for-scriptable/releases/download/1.0.1/bilibili.scriptable)后，用`scriptable`打开

### <a name='2.3-参数'></a>参数

小组件的parameter可以设置以下几个值

<table>
    <thead>
        <tr>
            <th>参数</th> <th>必填</th> <th>值/示例</th> <th>说明</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="3">type</td> <td rowspan="3">否</td> <td>番剧/global/进口</td> <td>进口番剧</td>
        </tr>
        <tr>
            <td>国创/cn/国产</td> <td>国产动画</td>
        </tr>
        <tr>
            <td>all/全部</td> <td>进口+国产</td>
        </tr>
        <tr>
            <td rowspan="2">onlyFollowed</td> <td rowspan = "2">否</td> <td>追番/true</td> <td>仅显示已追</td>
        </tr>
        <tr>
            <td>全部/false</td> <td>未追番 + 已追番</td>
        </tr>
        <tr>
            <td>uid</td> <td>当onlyFollowed为追番/true时 必填</td> <td>8165988</td> <td>Bilibili账号的UID，如果要设置仅显示追番，必须同时设定这个值。同时要设置空间公开显示番剧订阅</td>
        </tr>
    </tbody>
</table>

> 获取uid：B站APP - 我的 - 点击头像 - 详情

在小组件的编辑界面，按照以下格式进行配置

```javascript
// 配置格式
type,onlyFollowed,uid  //注意必须用英文逗号

// 示例
示例1: 国创,追番,8165988

示例2: cn,true,8165988

示例3: ,追番,8165988

示例4: ,true,8165988

示例5: 番剧,追番,8165988

示例6: global,true,8165988

示例7: 全部,追番,8165988

示例8: all,true,8165988
```

配置示例

![](preview/bilibili配置1.jpg)


![](preview/bilibili配置2.jpg)

## 小组件：LOL近期赛事列表

### 效果预览

![](./preview/LOL%E9%A2%84%E8%A7%88.PNG)

### 安装

下载[:link:安装脚本](https://github.com/Max-Sum/iOS14-widgets-for-scriptable/releases/download/1.0.1/lol.scriptable)后，用`scriptable`打开

## 小组件：深蓝SL03车辆状态

<font color="red"><b>声明</b></font>：
- 脚本所展示的信息不保证准确无误，锁车、充电、电量、油量等所有信息仅供参考，请勿将桌面组件展示的数据作为决策依据，由于脚本展示数据错误/误差造成的任何后果，本人概不负责。
- 脚本需要使用深蓝APP的登录信息来获取数据，安装即代表您同意脚本使用您的登录信息。
  - 所有数据只会存储在您的iCloud云盘或者手机本地，不会上传到任何第三方服务器。

### 效果预览

特性:
 - 支持 中/小 桌面组件 以及 锁屏组件
 - 桌面小组件展示车辆数据: 电池续航、油箱续航、总里程、车内温度(仅纯电车型)、车辆位置、车辆锁定状态、车辆充电状态、车牌号
 - 主题支持自动跟随系统黑暗模式切换
 - 锁屏组件展示车辆数据: 电量、油量
 - 点击桌面/锁屏组件跳转到深蓝APP控车界面
 - 自定义数据块内容，选择电量百分比、油量百分比、综合续航、剩余流量等

> 车型颜色需要收集比对各种颜色车子的抓包数据来判断是哪个字段，目前没有足够的数据支撑，所以统一白色，当然，小组件提供了部分[自定义选项](#43-主题设置自定义车辆图片logo型号文本)，你可以自己选择组件风格、车辆颜色、替换车辆图片。

简约风格
![](https://i.328888.xyz/2023/04/08/iR5RCU.jpeg)

模块化风格
![](https://i.328888.xyz/2023/04/05/i8cbho.jpeg)
![](https://i.328888.xyz/2023/04/05/i8c8ZN.jpeg)

自定义数据块
![](https://i.328888.xyz/2023/03/24/i4ZMcb.png)

### 安装

为了节省你的时间，<font color="red"><b>请认真阅读下面的操作步骤</b></font>，并依照文档进行操作，<font color="red"><b>跳过任何一个字都只会成倍地浪费你的时间</b></font>。为了帮助小白理解，最下面有抓包操作流程图。

安装组件和获取参数的操作过程对小白来说有一定的难度，但是文档写这么长就是为了让更多的人能顺利装上，只要跟着文档一步步操作就能成功。新手大概需要5～10分钟。


**认真阅读文档！不要跳过任何一步！**

**认真阅读文档！不要跳过任何一步！**

**认真阅读文档！不要跳过任何一步！**


为了顺利打开下面的链接，**请在safari浏览器中打开本页面**。

1. 确保iCloud是开启状态，
2. 安装[:link:Scriptable APP](https://apps.apple.com/cn/app/scriptable/id1405459188)
3. 下载[:link:桌面组件安装脚本](https://github.com/Max-Sum/iOS14-widgets-for-scriptable/releases/download/1.0.1/SL03Widget.scriptable)后，用`Scriptable`打开
4. 安装scriptable后会自动创建几个Demo脚本，其中有一个脚本是`Random Scriptable API`，先点击运行一次这个脚本。(如果没有看到`Random Scriptable API`脚本就在`Gallery标签页 -> Great WIdgets`里面添加)。
5. 按照下面章节讲的方法获取`Authorization`并设置到脚本中。

### 参数

- 桌面组件参数: `Authorization`
- 锁屏组件参数: `模式`
  - 非必填，可以填写:`电`、`油`，默认显示电量
  - 请先设置好桌面组件再使用锁屏组件

#### `Authorization`获取方法

##### 速通版本

对深蓝APP进行抓包，获取API`/appapi/v1/member/ms/cacToken`请求体header里面的`Authorization`，然后把token填入组件参数里就行了，组件高级功能在Scriptable APP里直接运行脚本就能看到。（如果你能看懂就不用看下面的了）

##### 详细版本

本组件需要获取`Authorization`，操作过程涉及抓包，幸运的是，<font color="green">IOS是抓包操作最简单的平台</font>，抓包方法我会讲。以桌面组件为例，`Authorization`获取及使用方法如下：

**为了你的数据安全请不要在公开场合发送抓包截图，拿到token相当于拿到了你的账号，通过token可以随时拿到你车子的定位和车门闭锁等数据，甚至可能直接操控车辆**


1. 安装[:link:Stream APP](https://apps.apple.com/cn/app/stream/id1312141691)，并开启<font color="red"><b>HTTPS抓包</b></font>功能，必须要显示“<font color="blue">设置成功：CA证书已经安装且信任</font>”。
![](./preview/HTTPS%E6%8A%93%E5%8C%85%E5%BC%80%E5%90%AF%E7%95%8C%E9%9D%A2.PNG)
1. 点击`开始抓包`
2. 打开`深蓝`APP，进入控车页面，下拉刷新车辆状态，为了确保请求能被抓到，建议多刷几次。
3. 回到`Stream` APP，停止抓包
4. 进入抓包历史，查看刚刚生成的抓包记录，搜索`cacToken`(注意搜索框里不要输入空格)，可以看到URI为`/appapi/v1/member/ms/cacToken`的请求
5. 点击查看请求详情，查看`请求-请求头部`
6. 将`Authorization`的<font color="red"><b>值</b></font>复制下来（比如你看到的是`Authorization : asd_iIAASHUDjmsdxxxxx`,这里要复制的就是`asd_iIAASHUDjmsdxxxxx`，千万不要复制多余的东西）
7. 打开`Scriptable`，运行脚本`SL03Widget`，选择`设置authorization`，粘贴刚刚复制的内容并保存
8. 回到桌面，新增桌面组件，创建Scriptable**中等大小**组件。
9.  在桌面**长按**上一步添加的小组件，在弹出菜单中选择**编辑小组件**，此时会出现小组件的设置界面，修改下面1项设置：
   -  `Script`：点击选择前面安装的脚本`SL03Widget`，
10.  点击空白处回到桌面，等待小组件完成加载。

> 锁屏组件目前只支持小号电量/油量圆环，锁屏组件的添加方法请参考[:link:视频教程](https://www.bilibili.com/video/BV19d4y1q7vi/?spm_id_from=333.337.search-card.all.click&vd_source=5b7cf4daa7d98506767a0757e0b64d77)进行操作。

<!-- ![](https://i.328888.xyz/2023/03/20/PjjEk.jpeg) -->

### 主题设置、自定义车辆图片、LOGO、型号文本...

目前支持自定义的内容：
- `型号`
- `LOGO`
- `车辆图片`

> <b>`车辆名称`</b>和<b>`车牌号`</b>是通过API获取的，如果你没有在`深蓝APP`中设置车牌号，小组件就拉不到车牌数据。所以这两个需要你自己在`深蓝APP`中修改，修改后等待系统刷新小组件即可。


![](https://i.328888.xyz/2023/03/20/Pjc43.jpeg)
![](https://i.328888.xyz/2023/04/05/i8cBAa.png)

### 地图API获取（仅大号组件需要）

1. 前往[高德开放平台](https://console.amap.com/dev/user/permission)注册账号，并认证个人开发者
2. 在[应用管理-我的应用]中创建一个应用命名为`sl03_widget`
3. 点击应用右侧的`添加`按钮，key名称设置为`sl03_widget_key`，服务平台选择Web服务，提交确认
4. 复制刚刚创建的`key`，输入到小组件的设置中，保存即可

### 常见问题

1. SSL错误？

设置-通用-传输或还原iPhone-还原-还原网络设置

2. 是不是自动刷新数据？

是，也不是。数据刷新分为两部分：1.你的车子把最新数据上传到深蓝APP的服务器数据库中，车子熄火断电后一般不会再更新数据，启动后会持续更新。2.小组件通过API获取数据库中的数据。

小组件只能控制第2部分的刷新，刷新频率由iOS系统自动调度控制。简单地说，你越关注小组件，小组件刷新频率越高。
> 小组件下方显示数据刷新时间就是为了在小组件信息滞后的时候提醒你这个数据不是最新的，避免引起进一步的误会。比如你刚锁车不到1分钟，可能看到小组件上面显示车辆是解锁状态，但是数据刷新时间能告诉你这是1分钟前的状态。


3. 能不能手动刷新数据？

可以实现，但非常不优雅，实用性太低，暂时不考虑做这方面的教程。
> 方法简单点说就是通过快捷指令触发Scriptable的“刷新全部组件”。


4. 能否控车？

可能有办法实现，但是鉴于法律责任风险，当前我不会去做更不会公开此类方法。

5. 点击桌面组件跳转非要先打开一下Scriptable吗？

是的，目前无法绕过，这是IOS系统层面的限制，如果后续系统升级放开相关限制我会更新的。
> 点击锁屏组件可以直接跳转到深蓝APP。

6. 为什么不做成独立的APP？

第一，时间成本，我的IOS开发经验不足，前端也不是主要专业方向，只是兴趣；第二，就算做出来了，不太可能通过AppStore的审核。

7. 为什么不做成模拟登录深蓝账号来拿token，这样小白也轻松很多？

法律风险太大。




> 本项目部分样式基于[bmw-scriptable-widgets](https://github.com/opp100/bmw-scriptable-widgets)开发，感谢作者的开源精神。