Npm Force Dependency Version by "npm-force-resolutions" Demo
============================================================

在npm中强制使用dependency的某个版本比较麻烦，不像yarn那样内置支持。

在npm中需要使用`npm-force-resolutions`作为辅助，而且做法也非常hacky：

1. 首先使用`npm install`安装，并生成`package-lock.json`
2. 运行`npx npm-force-resolutions`，修改`package-lock.json`中的相应版本
3. 删除`node_modules`，再次运行`npm install`会根据package-lock.json重新安装

感觉不是很好，算是没办法的办法。应该先试试更新相关的dependency版本来解决。

```
npm install
npx npx npm-force-resolutions
rm -rf node_modules
npm install
```

检查：

```
npm ls fsevents
```

使用的应该是`1.2.9`版本。
