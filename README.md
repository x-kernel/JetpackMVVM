# 2020年最新最实用的android-MVVM框架


<img src="https://img-blog.csdnimg.cn/20200421193001875.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1ZjU3Ryb25n,size_16,color_FFFFFF,t_70" width="300" align=center />
<img src="https://img-blog.csdnimg.cn/20200421193130501.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1ZjU3Ryb25n,size_16,color_FFFFFF,t_70" width="300" align=center />
<img src="https://img-blog.csdnimg.cn/20200421193154897.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1ZjU3Ryb25n,size_16,color_FFFFFF,t_70" width="300" align=center />
<img src="https://img-blog.csdnimg.cn/20200421193208122.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1ZjU3Ryb25n,size_16,color_FFFFFF,t_70" width="300" align=center />
<br/>
<br/>
java版mvp参见：https://github.com/VcStrong/RxRetrofitMVPDemo.git<br/>
kotlin版mvp参见：https://github.com/VcStrong/KotlinMVPDemo.git<br/>

## 1.mvvm-v1 2020.04.20
这是一个整合架构，所有功能开发都只能在一个module中

### 1.1 业务功能包含以下：
- 登录注册（跳转主页后关闭，已登录用户可直接进入主页）;
- 仿微信朋友圈，Recyclerview嵌套RecyclerView实现多图布局列表切换（一张横向全屏，二张横向全屏，三张横向全屏，四张分两行且横向全屏）；
- 发表朋友圈回传值刷新（viewmodel中livedata妙用）；
- 多图带参数上传；
- 首页和设置页分别退出登录（intent的flag使用）；

### 1.2 本架构技术功能包含以下：
- ViewModel在xml页面变量同一命名；
- Adapter中item的xml如果经常复用但model数据不一致的情况，切勿盲目binding设置，切勿单向页面绑定，请在adapter中手动控件赋值，不要xml-binding；
- Adapter中复杂控件处理需要大对象，建议灵活使用binding寄存，参见CircleAdapter类
- ObjectBox快速实现对象存取
- LiveData对网络请求数据灵活设置，view层基于观察者模式填充
- viewbinding中onClick，onCheckedChanged等事件使用，其他事件根据Listenter实现方法的名字举一反三

### 1.3 框架包含以下
- androidx：这个系列的jar包和appcompat.support对立的，参见谷歌官方文档
- lifecycle-viewmodel+lifecycle-livedata：生命周期管理，完全解耦，方便系统内存管理释放，基于观察者模式实现数据更新等等
- DataBinding
- retrofit2+rxjava2
- ObjectBox：android上运行速度最快的数据库，基于c/c++开发，native接口
- MZBanner：banner如果不需要刻意去掉。
- Fresco：图片加载
- XRecyclerView
- RxPmissions：权限申请比较好用
- Arouter：页面路由


## 2.mvvm-v2
v2版本计划在v1基础上进行组件化升级，不过目前v1版本并没有达到很高的集成标准，所以暂时主要工作放在对v1架构的思考和改进上。
