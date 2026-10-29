# 阿瓦隆 · 玩家记录台（PWA）

一个单页应用：记录每轮车队、票型、任务结果，并按角色给出建议。
装到手机主屏后可离线使用。

## 部署到 GitHub Pages

1. GitHub 新建仓库（Public），例如 `avalon`。
2. 把本目录下这 6 个文件上传到**仓库根目录**（不要上传文件夹本身）：
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `apple-touch-icon.png`
3. 仓库 **Settings → Pages**：
   - Source: `Deploy from a branch`
   - Branch: `main`，目录 `/ (root)`
   - 保存。
4. 等 1~2 分钟，页面顶部会出现地址：
   `https://<你的用户名>.github.io/avalon/`

## 装到手机

- **Android Chrome**：打开地址 → 菜单 → 「安装应用」或「添加到主屏幕」。
- **iPhone Safari**：打开地址 → 分享 → 「添加到主屏幕」。

首次打开需要联网（安装 Service Worker），之后断网也能开。

## 更新版本

改了页面后，记得把 `sw.js` 里的

```js
const CACHE = 'avalon-rec-v1';
```

改成 `v2`、`v3`……否则手机可能一直用旧缓存。

## 说明

- 数据存在浏览器本地（`localStorage`），换设备/换网址不会同步。
- 本应用与局域网版（`http://10.218.22.200/`）是两个不同的源，存档互不相通。
