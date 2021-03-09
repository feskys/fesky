# fesky-cli

> 版本 `@fesky/cli` 1.5.2.

## 介绍：

> 可以实现 vue、react 项目的自动化搭建；
>
> 可以实现基于 gulp 构建的模块化等多页面项目的搭建；

## 作者：

> 陈元广

## 查看 node 版本：

    "必须保证node在7.3以上版本"

## 下载安装

检查是否安装过 fesky-cli

```bash
    fesky -V
```

### 初次安装

```bash
    npm install -g fesky-cli
```

### 版本更新

使用插件进行更新

#### windows

这里采用的是最笨拙有效的方式（windows 权限问题很恶心）

> 1、先找到全局 npm 和 npm-cache(一般都在 C:\Users\用户名\AppData\Roaming)
>
> 2、删除 npm-cache(防止从缓存中读取 fesky-cli)
>
> 3、打开 npm 文件夹
>
> 4、把如下文件删除：fesky、vuecli、vuecli-init、reactcli、reactcli-init、mbcli、mbcli-init
>
> 5、打开 npm/node_modules 文件夹：删除 fesky-cli
>
> 6、再次进行全局安装

```bash
    npm install -g fesky-cli
```

#### mac

> 1、先找到命令所在的文件夹(一般都在/usr/local/bin/)
>
> 2、打开文件夹
>
> 3、把如下文件删除：fesky、vuecli、vuecli-init、reactcli、reactcli-init、mbcli、mbcli-init
>
> 4、打开/usr/local/lib/node_modules 文件夹：删除 fesky-cli
>
> 5、再次进行全局安装

```bash
    npm install -g fesky-cli
```

## 创建项目：

### react 项目创建：

#### template-name:

> 1、webpack：自动集成了所有的配置，在创建项目时，以询问的方式进行项目配置
>
> 2、normal：可以添加任何一种 react 模板，不具备创建项目时的询问

#### 创建

```bash
    reactcli init <template-name> [project-name]
    cd [project-name]
    npm install
    npm start
```

example：

```bash
    reactcli init webpack reactTest
    reactcli init normal reactTest
```

### vue 项目创建：

#### template-name:

> 1、webpack：自动集成了所有的配置，在创建项目时，以询问的方式进行项目配置
>
> 2、normal：可以添加任何一种 react 模板，不具备创建项目时的询问

#### 创建

```bash
    vuecli init <template-name> [project-name]
    cd [project-name]
    npm install
    npm start
```

example：

```bash
    vuecli init webpack vueTest
    vuecli init normal vueTest
```

### mb 项目创建(移动项目)：

#### 创建

```bash
    mbcli init [project-name]
    cd [project-name]
    npm install
    npm start
```

example：

```bash
    mbcli init mbTest
```

## 注：

#### template-name 为 webpack 的配置说明：

        name                   项目名称
        description            项目描述
        author                 项目作者
        email                  邮箱
        device                 项目平台
        host                   项目访问地址
        port                   项目端口号
        browerOpen             是否在浏览器中直接打开
        devtool                是否使用webpack的devtool调试代码
        cssType                是否使用sass，less进行css书写
        mock                   是否使用mock进行接口数据的模拟
        esLint                 是否使用esLint
        react-project-type
        # or
        vue-project-type       使用何种模板创建项目

### 使用 antd 时，在 config/config.js 的 babel：plugin 中添加如下配置：

```javascript
[
    'import',
    {
        libraryName: 'antd',
        libraryDirectory: 'es',
        style: 'css',
    },
];
```

### 使用 antd-mobile 时，在 config/config.js 的 babel：plugin 中添加如下配置：

```javascript
[
    'import',
    {
        libraryName: 'antd-mobile',
        style: true,
    },
];
```
