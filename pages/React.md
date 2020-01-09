##### 1、react中实现双向数据绑定

```
给输入框添加onChange事件 
编写事件代码 （改变绑定的值 this.setState）

```

##### 2、react点击事件传参

```
onClick={this.handleClick.bind(this, props0, props1, ...}

```

##### 3、redux的应用场景、工作流

```
应用场景：
1. 所有页面都要用的公共信息 ；
2. 一个页面又多个ajax ；
3. 不同组件之间期望不用通过组件代码通信

工作流：
   https://img2018.cnblogs.com/blog/1087883/201812/1087883-20181205145741397-1912744867.png
```

##### 4、在react中如何避免样式重叠

```
1、安装styled-components
2、创建一个样式组件
3、引入使用
```

##### 5、react和react-native之间的区别

```
1、标签：react-native不使用HTML来渲染App，但是提供了可代替它的类似组件
2、导航：react-native拥有自己的导航系统
3、react-native是基于react的移动端开发框架

```

##### 6、react-native引入网络图片

```
//网络图片
<Image source={{uri:"xxx"}}>
//Tips:图片相关的资源一定要加样式width,height
```

##### 7、react-native获取屏幕宽高

```
引入Dimensions
import { Dimensions } from 'react-native';
const { width, height,scale} =Dimensions.get('window');

```

