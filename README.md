# travel

#### 介绍
vue去哪儿实战小项目(本实战来自于慕课网vue2.5实战去哪儿教程)

使用了stylus语法
创建主页的组件，
1.建立主页的头部，轮播，内容组件; 城市搜索页组件的搜索，热门城市，显示城市的三组件，详情页组件的门票信息，图片内容，顶部内容组件
# 安装fastClick 解决移动端的点击 300 毫秒延迟问题，

1.npm install fastclick --save


![fastclick使用](https://images.gitee.com/uploads/images/2019/0512/095346_25066a72_4986174.png "屏幕截图.png")

2.使用styl创建全局变量css，  使通用的css引用

3.轮播图使用了GitHub上的 vue-awesome-swiper

4.用aixos请求本地数据或服务器的数据


5.在gitignore文件添加数据文件路径使文件不更新到git本地和线上仓库
![文件不更新到git](https://images.gitee.com/uploads/images/2019/0512/100111_b9856f4e_4986174.png "屏幕截图.png")

6.使用vuex实现home主页与city城市搜索组件的数据传递
![vuex的使用](https://images.gitee.com/uploads/images/2019/0512/100620_7837d99f_4986174.png "屏幕截图.png")

state公用数据，使用localStorage添加本地缓存防止重新调用， aciton使用dispatch   
try catch 在隐私模式时防止本地缓存报错
使用vuex高级API  {{mapxxxx}}  把city数据映射到计算属性xxxx如：currentCity中，就可以直接调用this.currentCity

keep-alive优化网页性能，使同样的数据ajax来回请求只请求一次，再使用keep-alive里的activated 函数 ，每次重新加载页面会加载，
 监听最后请求与当前城市是否相同，如果相同，则不加载，不相同，则把选择的页面重新加载

7.详情页列表，  使用递归组件，自己调用自己
![递归组件](https://images.gitee.com/uploads/images/2019/0512/101339_6fcfefdb_4986174.png "在这里输入图片标题")

8.真机调试，bug 修改，页面优化


首页
![首页展示](https://images.gitee.com/uploads/images/2019/0512/090949_5f766175_4986174.jpeg "WechatIMG1141.jpeg")

![城市搜索页](https://images.gitee.com/uploads/images/2019/0512/091009_e34caf0e_4986174.jpeg "WechatIMG1142.jpeg")

