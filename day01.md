# 1.vue-cli脚手架初始化项目
node + webpack + 淘宝镜像
1. node_modules文件夹：项目依赖文件夹
2. public文件夹：一般放置一些静态资源（图片），需要注意，放在public文件夹中的静态资源，webpack进行打包的时候，会原封不动打包到dist文件夹中
3. src文件夹（程序员源代码文件夹）：
   - assets文件夹：一般也是放置静态资源（一般放置多个组件公用的静态资源），需要注意，放置在assets文件夹里面静态资源，在webpack打包的时候，webpack会把静态资源当做一个模块，打包JS文件里面。
   - components文件夹：一般放置的是非路由组件（全局组件）。
   - App.vue：唯一的根组件，Vue当中的组件都是.vue
   - main.js：程序入口文件，也是整个程序当中最先执行的文件
4. babel.config.js：配置文件（babel相关）
5. package.json文件：认为是项目的“身份证”，记录项目叫做什么，项目当中有哪些依赖，项目怎么运行
6. package-lock.json：缓存性文件
7. README.md：说明性文件

# 2.项目的其他配置
## 2.1、项目运行起来的时候，让浏览器自动打开
```json
  "scripts": {
    "serve": "vue-cli-service serve --open",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  },
```
## 2.2、eslint校验功能关闭
为啥要关闭eslint校验功能呢？

其中一个原因是：声明变量但是不使用eslint校验工具，就会报错。
1. 在项目根目录创建`vue.config.js`文件；
2. 在里面配置：
```javascript
module.exports = {
	lintOnSave: false
}
```

## 2.3、src文件夹简写方法，配置别名：@
jsonconfig.json配置别名@提示【@代表的是src文件夹，这样将来文件过多，找的时候方便很多】
```javascript
{
	"compilerOptions": {
		"baseUrl": "./",
		"paths": {
			"@/*": ["src/*"]
		}
	},
	"exclude": ["node_modules", "dist"]
}
```

# 3.项目路由的分析

