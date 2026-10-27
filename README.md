# 贪吃蛇 · 安卓 APK

一个网页版的贪吃蛇，用 [Capacitor](https://capacitorjs.com/) 打包成安卓 App，**APK 由 GitHub Actions 自动构建**，不需要装 Android Studio。

## 下载安装

👉 打开 **[Releases · apk-latest](../../releases/tag/apk-latest)** → 点 `snake.apk` 下载

装到华为手机（HarmonyOS）前要做两件事：

1. 关闭纯净模式：**设置 → 系统和更新 → 纯净模式 → 退出**
2. 授权安装来源：**设置 → 安全 → 更多安全设置 → 安装外部来源应用 → 文件管理 → 打开**

然后到文件管理里点 `snake.apk` → 继续安装 → 桌面上出现「贪吃蛇」图标。

> ⚠️ 别用微信 / QQ 传 APK，它们会把文件名改成 `.apk.1` 导致装不上。用数据线、网盘，或者直接在手机浏览器打开本页下载。

## 玩法

滑动屏幕控制方向，吃红色的果子得分，撞墙或撞到自己就结束。每吃 5 个加速一档，最高分存在本地。

## 改游戏

改 `www/index.html`，提交到 `main` 分支，Actions 会自动重新打包，几分钟后 Releases 里的 `snake.apk` 就更新了。

## 工程结构

```
├── .github/workflows/main.yml   # 构建流水线（Capacitor + Gradle）
├── capacitor.config.json        # App 名称、包名、网页目录
├── package.json                 # 依赖
└── www/index.html               # 游戏本体（全部代码都在这）
```

包名 `com.feiyu.snake`，Debug 签名（自用安装足够）。
