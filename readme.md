# 项目结构
config/ 目录下的config.js默认为全局的配置
mock/   模拟后端请求数据的js目录
src/    代码目录
pages/  前端页面，页面的后缀名可为.js或.jsx
models/ 数据层，处理数据的js文件
layouts/默认是整个页面的基础布局

# 分层开发
用户 -> Page -> Model -> Service

## Page 
- 负责面向用户：渲染页面、接受用户的操作和输入，侧重于展示型交互逻辑
- 使用 UmiJS 的 umi-plugin-react 的 diva 功能，可以调用Model层定义的数据和方法

## Model
- 负责处理业务逻辑，为Page做数据、状态的读写、变换、暂存等
- 使用 import 定义的异步请求函数 request.js 调用service层

## Service
- 负责与 HTTP 接口对接，进行纯粹的数据读写。
- service从后端请求数据