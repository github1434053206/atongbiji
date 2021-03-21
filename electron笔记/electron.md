# 安装electron,使用electron

安装：

cnpm install -g electron

使用：

看pdf.

Electron 安装  运行.pdf

组最方法：

npx creatr-electron-app myelectron

用npm start运行electron项目

crtl+r命令可以快速刷新

# 安装yarm

cnpm i -g yarn

# packpage.json快速生成

npm init --yes

# Eslint代码检测工具

看pdf和b站https://www.bilibili.com/video/BV12t411e7sQ?p=3

# Electron 运行流程、主进程渲染进程、通过nodejs读取本地文件、开启调试模式

看pdf和b站

https://www.bilibili.com/video/BV12t411e7sQ?p=4

Electron 运行流程、主进程渲染进程、读取本地文件、开启调试模式.pdf

nodejs只有在主进程中默认使用，要想在渲染进程中使用则需要

```javascript
const createWindow = () => {
  // Create the browser window.
  const mainWindow = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences:{ //让渲染进程使用
      nodeIntegration:true
    }
  });
```

# npm-如何快速下载packjson里的包

直接cnpm i

# electrion拖拽事件

看pdf：

调用h5的拖放api 结合nodejs fs实现拖放打开文件功能.pdf

和视频

# 开启一个新窗口

```javascript
const{ remote } = require("electron")
const Brow = remote.BrowserWindow;
const path = require('path');

let suv = document.getElementById("ios")
    suv.onclick= ()=>{
        const news = new Brow({
            width: 800,
            height: 600,
            webPreferences:{ //让渲染进程使用
              nodeIntegration:true,//
              enableRemoteModule:true//开启渲染进程用remote方法
            }
    })
    news.loadFile(path.join(__dirname, 'index.html'));
}
```

# 接下来要花时间学习

