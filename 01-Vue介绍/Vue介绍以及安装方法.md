# Vue 介绍

## Vue 是什么？

Vue 是一种用于构建用户界面的渐进式框架。它的核心库专注于视图层，易于与其他库或现有项目集成。Vue 的两个主要特点是：

- 数据绑定：Vue 提供了一种机制，可以将数据与 DOM（文档对象模型）元素绑定在一起。例如，当你更改输入框（Input）的值时，所有绑定到该输入框的元素的值都会自动更新。
- 组件化：Vue 允许你将页面分解为可重用的组件，每个组件都可以是一个单独的 .vue 文件。这些组件可以像乐高积木一样组合在一起，构建复杂的用户界面。

## Vue2 的推荐开发环境

以下是一些推荐的开发工具和环境：

- Homebrew：对于 Mac 系统，Homebrew 是一个优秀的包管理器，类似于 Linux 的 apt-get 或 Windows 的控制面板，用于安装和删除应用程序。
- Node.js：JavaScript 的运行环境，用于执行 JavaScript 代码。
- npm：Node.js 的包管理器，用于安装和管理 Node.js 包。
- webpack：一个模块打包工具，用于将 Vue 的 .vue 组件或其他自定义组件转换为浏览器可以解析的 .js 文件。
- vue-cli：一个用于生成 Vue 项目模板的命令行工具。

## 如何安装 Vue

### 安装 Node.js

首先，你需要安装 Node.js。以下是使用 NVM（Node Version Manager）安装 Node.js 的步骤：

1. 下载 NVM 安装包：访问 NVM for Windows 的 GitHub 页面，选择 nvm-setup.exe 或 nvm-setup.zip 文件下载。
2. 运行安装程序：双击 nvm-setup.exe 文件，按照提示进行安装。你可以选择安装路径，这里假设安装路径为 C:\NVM。
3. 验证安装：安装完成后，系统环境变量中会新增两个变量 - NVM_HOME（存储 NVM 的根路径）和 NVM_SYMLINK（存储当前使用的 Node.js 的符号链接路径）。注意，PATH 环境变量中会自动添加 %NVM_HOME% 和 %NVM_SYMLINK%，你可以直接使用 nvm 命令。
4. 检查 NVM 版本：打开命令提示符，输入 `nvm version` 查看 NVM 版本。

接下来，使用 NVM 安装 Node.js：

1. 查看可用的 Node.js 版本：输入 `nvm list available`。
2. 安装 Node.js：你可以选择以下三种方式来安装 Node.js：
   - 安装最新版本：`nvm install node`
   - 安装最新 LTS（长期支持）版本：`nvm install --lts`
   - 安装指定版本：`nvm install <version>`
3. 验证 Node.js 安装：检查 Node.js 和 npm 的版本，输入 `node -v` 和 `npm -v`。

### 安装 Vue

在安装 Vue 之前，首先检查 Node.js 和 npm 是否已经成功安装。在命令行中输入 `node -V` 和 `npm -V`，如果显示出版本信息，那么安装成功。

接下来，安装 vue-cli 和 webpack：`npm install vue-cli -g` 和 `npm install webpack -g`。

### 创建 Vue 2.x 项目

使用 vue-cli 根据模板创建项目：

```shell
vue init webpack-simple <项目名称>
npm install
npm install vue-router vue-resource --save
npm run dev
```

### 常见的依赖安装命令

以下是一些常见的 Vue 项目依赖的安装命令：

```shell
axios: npm install axios
element-ui: npm i element-ui --save
vue-router: npm install vue-router --save
vuex: npm install vuex --save
mavon-editor: npm install mavon-editor --save
markdown-it: npm install markdown-it --save
github-markdown-css： npm install github-markdown-css --save
VCharts: npm install v-echarts echarts --save
```