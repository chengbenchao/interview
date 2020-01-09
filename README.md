# docsify教程

## 一、安装依赖

```
npm i docsify-cli -g
```

## 二、初始化项目

```
docsify init
```

## 三、启动

```
docsify serve
```

## 四、配置

#### 4-1 配置侧边栏

```js
//在 index.html 文件配置 loadSidebar 选项
window.$docsify = {
      loadSidebar: true,
      name: '前端面试'
}
```

```md
//2.在项目根目录下新建_sidebar.md文件，内容如下
* [html-css](pages/html-css)
* [Javascript](pages/Javascript)
* [vue](pages/Vue)
```

```js
//3.配置文档目录
window.$docsify = {
    loadSidebar: true,
    subMaxLevel: 6
}
```

```js
//html-css.md中随便写几个标题,就可以看到目录的层级
# html
## css
### css-1
#### css-2
```

#### 4-2 配置导航栏

```
//1.在 index.html 文件配置 loadNavbar 选项
window.$docsify = {
      loadNavbar: true,
      name: '前端面试'
}
```

```
//2.在项目根目录下新建_loadNavbar.md文件，内容如下
* [html-css](pages/html-css)
* [Javascript](pages/Javascript)
* [vue](pages/Vue)
```

#### 4-3 设置封面

```
//1.配置index.html的
window.$docsify = {
      coverpage: true
}
```

```
//2.新建_coverpage.md文件,配置如下
![logo](assets/logo-s.svg)

# 前端面试宝典

> 涉及以下技术栈

* HTML-CSS-Javascript
* React
* Angular
* React-native
* Flutter
* Ionic

[码云](https://gitee.com/chengbenchao)
[语雀](https://www.yuque.com/chengbenchao)
[Get Started](pages/html-css)
```

#### 4-4 配置主页,合并导航

```js
window.$docsify = {
      repo:"https://gitee.com/chengbenchao",
      mergeNavbar:true,
      homepage:"pages/html-css.md"
    }
```

#### 4-5 配置搜索框

```js
//index.html中进行配置
<script>
    window.$docsify = {
      search:{
        paths:["auto"],
        maxAge: 86400000,
        placeholder: '请搜索',
        noData: '没有搜索到你想要的结果',
        depth:6
      }
    }
</script>
<script src="//unpkg.com/docsify/lib/docsify.min.js"></script>
<script src="//unpkg.com/docsify/lib/plugins/search.min.js"></script>
```

