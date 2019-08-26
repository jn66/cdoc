---
weight: 2
template: docs
title: 手机知网专题站
---

# 手机知网-专题站使用文档

专题站是手机知网WAP、手机知网app的二级专题网站，本平台能够让编辑自动化的生成专题内容，通过调用接口，自动化的生成不同的专题站，最终完成专题站的部署、上线。
本系统包含两个部分，一个部分是通过后台自动生成json模板，让编辑填充图书code，另一部分是通过code，调用接口，完成主题的自动生成。


## 上手指南
以下指南将帮助你在本地机器上安装和运行该项目，进行开发和测试。

## 技术选型

本系统是前后分离的纯前端页面，通过axios调用接口，完成内容的获取，并通过vue的模板引擎，渲染到页面上。

- 前端框架 Vue

### 安装要求

- 文本编辑器 Visual Studio Code (其他编辑器也可)
- Node.js  10.14.1 版本以上
- NPM 使用淘宝镜像CNPM

  
### 安装步骤

- 下载[Visual Studio Code](https://code.visualstudio.com/) 并安装到本地
- 下载[node.js](https://nodejs.org/en/)并安装到本地
- 使用淘宝镜像CNPM
  ```
  npm install -g cnpm --registry=https://registry.npm.taobao.org
  ```
- 在项目文件目录下，完成依赖包包安装
  ```
  cnpm install
  ```
- 开发时运行  
  ```
  npm run serve
  ```

- 部署上线
```
npm run build
```

## 项目部署

依据产品经理的要求，和后台开发人员规定部署方式，使用svn/git/syncToy 2.1，或者直接打包交给开发进行再次开发和部署。

## 项目更新
- 2019.5.15 可以根据给定的数据，自动生成专题页面，完成主题生成器的开发
- 2019.5.20 完成json数据生成器的开发，编辑可以在此自动生成数据。

## 新专题上线方法

- 假如本次上线的新专题为demo
- 编辑利用后台，/tool.html 生成可使用的数据格式。
- 把这个数据重命名为  demo.js  放在./src/data下，每次需要重新起一个英文名字。
- HTML：在public下，新建demo.html,内容复制别的主题。修改title、keywords、description、和微信分享的字段。
- JS：在./src/pages/目录下，新建demo.js ,内容复制自别的主题。import App from '@/views/xxx.vue'， 修改成本主题的内容 import App from '@/views/demo.vue'
- Vue: 在./src/views目录下，新建demo.vue, 内容复制自别的主题。修改引入数据的路径。import mydata from "../data/xxx.js"; 修改为 import mydata from "../data/demo.js";
- 路由: vue.config.js下，新建路由字段
  ```
  demo:{
      entry: 'src/pages/demo.js',
      template: 'public/demo.html',
      filename: 'demo.html'
    }
  ```

## 项目负责
产品经理：王瑞

前端开发：姜宁

后端开发：颜贻通

如有任何问题，请于以上人员联系。

## 版权说明
本项目版权由《中国学术期刊（光盘版）》电子杂志社有限公司所有

## 鸣谢
《中国学术期刊（光盘版）》电子杂志社有限公司  

同方知网（北京）技术有限公司  

同方知网数字出版技术股份有限公司
