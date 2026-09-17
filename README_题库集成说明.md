# 工控面试题库 · GitHub Pages 集成说明

把 **50,042 题工控面试题库** 集成到 t84RT.github.io（小吴同学电气设计主页）。

## 本次改动内容

```
t84RT.github.io/
├── index.html                  ← 已修改：新增"工控面试题库"入口卡片（最新动态板块上方）
└── interview-bank/             ← 新增：题库子页面（独立部署，不动首页结构）
    ├── index.html              题库全量浏览器（搜索/筛选/分页/展开答案）
    ├── statistics.html         题库数据看板（分类/难度/来源图表）
    ├── assets/                 公众号/小程序二维码（gzh-qr.png、mini-qr.png）
    └── data/                   题库数据分片（12 个 js，共约 68MB，勿改动）
        ├── bk_00.js ~ bk_11.js
```

两个题库页面底部均新增 **"关于 小吴同学电气设计"** 信息区块（深色科技风）：
- 名称/定位/简介 + 身份徽章（独立工具开发者/电气效率极客/工控PLC伺服/全端覆盖）
- 商务邮箱 xiaowu112899@outlook.com、微信公众号"小吴同学电气设计"（微信搜一搜横幅物料）、微信小程序"小吴同学电气设计工具"（二维码）
- 平台矩阵（抖音/B站/CSDN/GitHub @t84RT）、服务方向标签、版权行

## 访问密码（AES-256 真加密）

题库数据已用密码做 **PBKDF2(10万次迭代) + AES-256-GCM 真加密**：

- 源码中**不存在任何密码痕迹**（无明文、无哈希），只有固定 salt/迭代参数
- 12 个数据分片全部为**密文**，且**文件名随机混淆**（`data/bk_<随机8位>.js`，源码中文件名经 base64 编码 + 随机顺序，无法按规律批量下载）
- 密码正确 → 浏览器本地派生密钥 → 解密全部数据 → 展示；密码错误 → 解密失败，什么都看不到
- **当前访问密码：`Xw2026@Gongkong#PLC`**（已从默认弱密码更换，含大小写/数字/符号，抗字典爆破）
- 换密码：用 `_work/reencrypt_shuffle.js` 重新加密（node reencrypt_shuffle.js <新密码> <saltHex>），
  脚本会自动重命名分片并输出新的 CHUNK_FILES 映射，粘贴进 index.html 即可
- 看板页（statistics.html）数据量小、不含完整题库，仍用哈希门保护（如需同等级加密可另行处理）

## 反调试·防F12 + 开发者控制台彩蛋

两个题库页面内置 **6 类反调试检测**，一旦检测到调试行为：

1. **弹窗引流**：弹出 8 个引流页面（主页 + 各平台搜索"小吴同学电气设计"），8 秒节流
2. **控制台彩蛋**：打开开发者工具即打印品牌 LOGO 横幅，随后**每 300ms 疯狂轮播**你的信息（公众号/小程序/邮箱/抖音/B站/CSDN/GitHub/服务方向），持续不停
3. 快捷键 F12 / Ctrl+Shift+I / Ctrl+Shift+J / Ctrl+Shift+C / Ctrl+U / Ctrl+S
4. 右键菜单"检查"入口
5. 窗口尺寸突变（F12 停靠面板）
6. debugger 计时检测 + 控制台刷屏

弹窗目标与播报内容在页面末尾 `FLOOD_URLS` / `EGG_INFO`（可替换成你的真实主页链接和更多信息）。

## 反 AI 抓取·无头浏览器/爬虫检测

两个页面在 `<head>` 内置**早期阻断**：检测到无头浏览器/爬虫特征（User-Agent 含 headless/phantom/puppeteer/playwright/selenium/curl/wget/python 等，或 `navigator.webdriver=true`）时，**直接返回"页面加载失败"假页面**——不输出密码门、不加载任何数据，AI 分析工具拿到的是空壳。

## 部署方法（3 条命令）

在仓库根目录（本文件夹）打开终端：

```bash
git add -A
git commit -m "新增工控面试题库(50,042题)子页面与首页入口"
git push origin main
```

推送后等 1~2 分钟 GitHub Pages 自动部署，访问：
- 首页入口：https://t84rt.github.io/ （往下滚动到"最新动态"上方即见题库入口卡片）
- 题库直达：https://t84rt.github.io/interview-bank/
- 数据看板：https://t84rt.github.io/interview-bank/statistics.html

## 说明

- 首页入口卡片链接到 `interview-bank/` 相对路径，本地预览与线上效果一致。
- 题库子页面首次打开需加载约 68MB 分片数据（GitHub Pages 自动 gzip 压缩传输，实际流量约 15~20MB），有加载进度条；之后浏览器缓存，秒开。
- 题库页顶有"返回主页"和"数据看板"链接，浏览完可一键回首页。
- 数据分片是题库内容，修改请直接改题库源文件后重新生成；子页面 UI 可随时调整。
