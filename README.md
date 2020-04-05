## 体验地址
[请先看完使用说明再点哦~~](http://recalendar.xyz:5000/)
## 这是个啥?

这是我尝试了几乎所有背单词软件后而不得不自己给自己写的一个背单词的小工具。

换句话说，就是目前为止没有一个背单词的软件能满足我的需求，于是我就在别人项目的基础上给自己写了一个。

那么你可能要问了，你的需求到底是啥？

我的需求是：

1. **能够在浏览器上随时添加我要背的单词**。
2. **要复习的每一个单词都要严格的遵循遗忘曲线**。

这两个需求缺一不可(没错，我就是产品眼中最难伺候的用户~~叉腰.jpg)

## 咋用啊？
### 安装
- 首先，你需要手动注册ID号和密码（ID号尽量为纯数字，不然mangoDB数据库没法分配）

- 然后[点击这里](https://www.jixieclub.com/res/other/dist.rar)，将“定制版”的达达翻译插件下载下来。
(这里安利一下原作者的项目，真的非常优秀，是我见到过的最漂亮的翻译插件，感兴趣的小伙伴可以去给大佬点个star！)

- 最后用chrome加载你刚才下下来的插件，登录你注册的ID号，就可以使用啦！

PS：建议在登陆完之后，将浏览器重启一下。
PPS: 由于服务器的奇怪原因，第一次发送登录请求可能会出现“用户不存在”，此次再点一下登录就好了。
### 具体使用
#### 添加单词
和达达翻译的原功能一样，只不过在当你点收藏的时候会将单词发送到ReviewCalendar。
![](https://www.jixieclub.com/res/img/re2.PNG)

#### 复习单词
每个添加进去的单词都会强制性的复习4次。
这四次出现的时间点分别是：

- 1天后
- 3天后(相对于上一次复习)
- 7天后(相对于上一次复习)
- 30天后(相对于上一次复习)

最终的效果就是这样
![](https://github.com/SeekingLight233/ReviewCalendar/blob/master/client/re3.PNG)
## 抱歉，我还是没看懂这玩意儿咋用。。
首先，今天是3.29号，右面的单词框是我今天要复习的单词，圈白色圈圈的日期代表有单词需要复习(当然没到那一天就不要提前复习了)
每当你复习过一个单词(具体表现为把单词点开，就像前三个那样)，待复习单词的生命周期就会-1(总共的生命周期为4)。

## 用到的轮子
[vue-event-calendar](https://github.com/GeoffZhu/vue-event-calendar)

将这位大大的日历组件中的单个event进行了改写，根据个人需求拓展了组件的`props`。

[dadda-translate-crx](https://github.com/waynecz/dadda-translate-crx)

达达翻译的原版本，原版本中如果收藏的单词过多，在打开浏览器的时候就会弹出非常多的单词吐司，甚至会造成浏览器卡顿，所以在定制版里我直接在代码里将弹吐司的功能给关闭了。
## 已知问题与Todo
- [ ] 将收藏按钮换成“续命”，当单词生命周期为1时，如果还没有记下来可以选择重新复习(不过这类单词应该很少)
- [ ] 移动端样式优化
- [ ] 更换翻译插件的翻译api，有的时候如果点一个单词没有翻译或者翻译的内容是乱码，此时需要手动进入[搜狗翻译](https://fanyi.sogou.com/)输入验证码。
