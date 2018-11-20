# egg使用教程

## 1 快速初始化

```
npm i egg-init -g
egg-init egg-example --type=simple
cd egg-example
npm i
```

## 2 逐步搭建
### 1 初始化项目
先来初始化下目录结构：
```
mkdir egg-example
cd egg-example
npm init
npm i egg --save
npm i egg-bin --save-dev
```
添加npm scripts到package.json:
```
{
    "name":"egg-example",
    "scripts":{
        "dev":"egg-bin dev"
    }
}
```
### 2 编写Controler
```js
// app/controller/home.js
const Controller = require('egg').Controller;

class HomeController extends Controller {
    async index() {
        this.ctx.body = 'Hello world';
    }
}

module.exports = HomeController;
```
配置路由映射：
```js
// app/router.js
module.exports = app => {
    const { router, controller } = app;
    router.get('/', controller.home.index);
};
```
加一个配置文件：
```js
// config/config.default.js
exports.keys = <此处改为你自己的Cookie安全字符串>;
```
此时目录机构如下：
```
