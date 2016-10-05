# listView
列表组件
=====
1、分页；2、列宽拖拽；3、序号列自动生成；4、单选和多选；5、列表头固定，以便在列表区域滚动的时候，列表头不会受滚动的影响；6、树形列表；7、列表各种事件等。
（1）带分页工具栏的列表组件；
（2）在（1）的基础上去掉了分页工具栏，改成了利用window的滚动事件进行滚动翻页，当然为了留一个后路，这个组件提供了加载更多这样的手工进行下一页的按钮；
（3）适用于移动端，由于移动端scroll事件必须得等到屏幕的滚动操作完全停止下来以后才会触发，所以不能直接利用window的滚动事件，而改用了iscroll插件来模拟滚动，同时利用它提供的scroll事件来实现更加快速响应的滚动翻页功能。
在实际使用中，要使用某一个类型的列表的时候，基本上只要使用simpleListView,tableView,scrollListView,iscrollListView即可。
一、文件结构：
______
1、base/listViewBase
它是所有列表组件的基类，基本上所有公共的事情都是在它里面处理的，比如排序组件初始化，分页组件初始化，模板引擎管理组件初始化，以及请求发送和请求解析等。每一个具体的列表管理组件都需要继承它。在这个类里面使用了模板方法的设计模式，以及在请求数据的前后，添加了多个事件回调，目的是为了子类能够进行灵活的个性化扩展。
