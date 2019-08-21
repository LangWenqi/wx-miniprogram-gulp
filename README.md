## wx-miniprogram-gulp
>基于Gulp构建的微信小程序开发工作流

### 特性

+ 基于`gulp+scss`构建的微信小程序工程项目
+ 项目图片自动压缩
+ ESLint代码检查
+ 使用命令行快速创建`page`、`template`和`component`
+ 支持生产环境打包

### Getting Started

##### 0. 开始之前，请确保已经安装node和npm，全局安装gulp-cli
```
$ npm install --global gulp-cli
```
##### 1. 下载代码
```
$ git clone https://github.com/LangWenqi/wx-miniprogram-gulp.git
```
##### 2. 进目录，安装依赖
```
$ cd wx-miniprogram-gulp && npm install
```
##### 3. 编译代码，生成dist目录，使用开发者工具打开dist目录
```
$ npm run dev （开发环境打包）
$ npm run test (测试环境打包)
```
##### 4. 新建page、template或者component
```
  gulp auto -p mypage           创建名为mypage的page文件
  gulp auto -t mytpl            创建名为mytpl的template文件
  gulp auto -c mycomponent      创建名为mycomponent的component文件
  gulp auto -s index -p mypage  复制pages/index中的文件创建名称为mypage的页面
```
##### 5. 上传代码前编译
```
$ npm run build （生产环境打包）
```
##### 6. 上传代码，审核，发版

### 工程结构
```
wx-miniprogram-boilerplate
├── dist         // 编译后目录
├── node_modules // 项目依赖
├── src 
│    ├── components // 微信小程序自定义组件
│    ├── env        // 请求域名配置
│    ├── images     // 页面中的图片和icon
│    ├── pages      // 小程序page文件
│    ├── styles     // ui框架，公共样式
│    ├── template   // 模板
│    ├── utils      // 公共js文件
│    ├── app.js
│    ├── app.json
│    ├── app.scss
│    ├── project.config.json // 项目配置文件
│    └── api.config.js       // 项目api接口配置
├── .gitignore
├── .eslintrc.js
├── package-lock.json
├── package.json
└── README.md

```

### Gulp说明

```
Tasks:
  dev              开发编译，同时监听文件变化
  test             整体编译，请求指向测试环境
  build            整体编译

  clean            清空产出目录
  wxml             编译wxml文件（仅仅copy）
  js               编译js文件，同时进行ESLint语法检查
  json             编译json文件（仅仅copy）
  wxss             编译less文件为wxss
  img              编译压缩图片文件
  watch            监听开发文件变化
  devEnv/testEnv/prodEnv 生成对应环境的请求域名配置

  auto             自动根据模板创建page,template或者component(小程序自定义组件)

gulp auto 

选项：
  -s, --src        copy的模板                     [字符串] [默认值: "_template"]
  -p, --page       生成的page名称                                       [字符串]
  -t, --template   生成的template名称                                   [字符串]
  -c, --component  生成的component名称                                  [字符串]
  --msg            显示帮助信息                                           [布尔]

示例：
  gulp auto -p mypage           创建名为mypage的page文件
  gulp auto -t mytpl            创建名为mytpl的template文件
  gulp auto -c mycomponent      创建名为mycomponent的component文件
  gulp auto -s index -p mypage  复制pages/index中的文件创建名称为mypage的页面
```

#### Q&A

- **Q:** `_template`目录的文件有什么用？


  **A:** 使用`gulp auto`命令自动生成文件，`-s`参数可以指定copy的对象，默认情况下是以对应目录下文件夹为`_template`中的文件为copy对象的。开发者可以根据业务需求，自定义`_template`下的文件。


- **Q:** `_template`目录的文件是否会被编译到`dist`目录？


  **A:** 不会。

