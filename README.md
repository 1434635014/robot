## 主要构造
- 眼睛
```bash
深度学习神经网络（无监督）进行图片识别，这一步骤主要对图片的数据进行提取，载体为摄像头
```

- 鼻子
```bash
深度学习神经网络（无监督）进行气味识别，这一步骤主要对气味的数据进行提取，载体目前就叫它气味收集器吧
```

- 耳朵
```bash
深度学习神经网络（无监督）进行语音识别，这一步骤主要对声音的数据进行提取，载体为类似麦克风的东西
```

- 嘴巴
```bash
此步骤最为简单，用文字转语音就行，载体就是音响
```

- 大脑
```bash
主要用强化学习，对眼睛鼻子耳朵这三个接收器所反馈的数据进行分析聚类，识别等操作，载体为软件程序
```
## 思路

```bash
眼睛和鼻子主要收集信息，但不对这些信息进行识别，仅仅只是将数据反馈给大脑，而耳朵除了收集数据信息之外，还能对类似“这个是...”这样的学习数据用额外的通道反馈给大脑，大脑将会对此前看到的信息进行匹配，学习
```
```bash
在此，可以看到，大脑首先要具备一定的语言处理能力，这个需要用监督学习提前训练出能处理基本语言的能力，来为大脑程序的匹配学习提供一定的支持
```
```bash
眼睛其实也可以进行收集学习信息，例如手语这种，不过这类的集中处理还是需要大脑提供一定的学习能力的支持
```

- [React](https://doc.react-china.org/docs/hello-world.html)
- [React router v4](http://reacttraining.cn/web/example/basic)
- [Redux](http://cn.redux.js.org/)
- [prop-types](https://github.com/facebook/prop-types)
- [immutability-helper](https://github.com/kolodny/immutability-helper)

## 目录说明
```bash
src
├── assets/         # 资源文件夹(scss、images)
│   ├── icons/
│   ├── images/   
│   └── style/ # 注：基本的布局类和公共类，这部分不要自己写
│
├── components/     # 组件
│   ├── base/   # 功能组件
│   └── common/ # 公用业务组件
│
├── config/         # 配置/常量
│
├── extends/        # Component/PureComponent原型扩展（可以直接在组件内部通过this访问扩展属性和方法：以$_开头）
│
├── interceptors/   # 拦截器      
│
├── locales/        # 国际化
│
├── mocks/          # mock数据
│
├── redux/          # redux (reducers/下每个文件为一个模块，相应的state通过store.<模块名/文件名>访问)
│
├── routers/        # router入口
│
├── services/       # api接口等
│
│── utils/          # 工具类、函数
│
├── views/          # 视图组件
│
├── App.js          
│
└── index.js        # 项目入口文件
```

## 关于views下的目录结构约定
```bash
# 文件夹的命名规则：除模块和页面的文件夹以外全部以_开头命名

views
├── <模块名>/
│   ├── _assets/     # 当前模块资源
│   │
│   ├── _config/     # 当前模块配置文件和常量
│   │
│   ├── _components/ # 当前模块组件
│   │
│   ├── _containers/ # 当前模块状态容器组件
│   │
│   ├── <页面名>/
│   │   └── ...      # 同`<模块名>/`下的结构（只是作用范围为当前页面）
│   │
│   └── index.js # 模块入口页面（譬如模块页面导航页，不一定有）
```


## debugger
### vscode
> .vscode/launch.json

需配合vscode插件[Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
```json
{
  "version": "0.2.0",
  "configurations": [
    {
    "name": "Chrome",
    "type": "chrome",
    "request": "launch",
    "url": "http://localhost:3000",
    "webRoot": "${workspaceRoot}/src",
    "sourceMapPathOverrides": {
      "webpack:///src/*": "${webRoot}/*"
    }
  }]
}
```