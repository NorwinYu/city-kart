# 落日环线 · Sundown Circuit

一个完整的 3D 城市卡丁车游戏：**3 圈、6 台卡丁车、860 米环城街道、漂移蓄能、氮气、动态清扫车、施工路障、AI 对手、胜利/失败/DNF 结算、移动触控**。

游戏本体是一个自包含的 HTML 文件，不加载任何外部图片、字体、模型或音频，也不包含追踪或分析代码。

## 在线结构

- `index.html` — 可玩的游戏（GitHub Pages 根页面）
- `features.html` — 全部游戏功能的高品质实机截图
- `iterations.html` — 从原型到最终版本的迭代过程，以及使用的 Skill
- `screenshots/` — 页面引用的全部本地画面（WebP）
- `.nojekyll` — 让 GitHub Pages 不经 Jekyll 处理静态文件（部署源使用分支时有用）

## 发布到 GitHub Pages

1. 在 GitHub 新建一个空仓库。
2. 把本文件夹里的所有内容放到仓库根目录并推送：

```bash
git init
git add .
git commit -m "Publish Sundown Circuit"
git branch -M main
git remote add origin https://github.com/<your-account>/<your-repo>.git
git push -u origin main
```

3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment** 中选择 **Deploy from a branch**。
5. 分支选择 **main**，目录选择 **/(root)**，保存。
6. 等待约一分钟，在 **Settings → Pages** 顶部查看站点 URL。
7. 发布完成后，入口是 `index.html`，全功能截图页是 `features.html`，制作记录是 `iterations.html`。

> 首次启用 Pages 必须由仓库管理员在 GitHub 设置中完成；普通的 `git push` 或仓库内的临时令牌没有创建 Pages site 的管理员权限。

> 将 `<your-account>` 和 `<your-repo>` 替换为你自己的账号和仓库名。本文件夹不包含账号名、电子邮箱、服务器地址或任何个人资料。

## 操作

| 输入 | 动作 |
|---|---|
| `W` / `↑` | 油门 |
| `S` / `↓` | 刹车 / 倒车 |
| `A` / `D` 或 `←` / `→` | 转向 |
| `Space` | 按住漂移蓄能，松开释放 |
| `Shift` | 氮气冲刺 |
| `R` | 脱困回赛道 |
| 鼠标拖动 | 环视 / 调整追尾相机 |
| `Esc` | 暂停 |
| `M` | 静音 |

触屏：方向、刹车、漂移、氮气与油门。

规则：前三名登上领奖台；第 4–6 名或耐久归零算失败。最佳圈速、名次、完赛次数与设置保存在本机 `localStorage`。

## 制作方法与 Skill

制作使用 **`photoreal-game` skill** 的工程流程：产品优先的完整游戏外壳 → 固定机位视觉检查 → 光照与城市密度迭代 → 碰撞/试玩/移动端/性能验证 → 单文件交付。Skill 是流程和验收方法，不是素材包。

本项目所有城市、卡丁车、招牌、贴图、UI、粒子和声音均由代码实时生成；没有从参考图、商业游戏、模型库、字体库或录音中提取素材。美术方向选择“电影感街机”而非照片复刻。

第三方运行时仅包含 **Three.js**，其许可证见 `THIRD_PARTY_NOTICES.md`。

## 隐私

- 无统计、无追踪、无 Cookie、无第三方请求。
- 不使用外部字体或 CDN。
- 不包含任何个人信息；请只将本文件夹发布到 Pages。
- `localStorage` 仅存储本机游戏设置与最佳成绩，数据不会离开浏览器。

## 技术

WebGL / Three.js、程序化 Canvas 纹理、自定义日落天空与云层 shader、PMREM 环境光、MSAA、UnrealBloom、ACES、自写颗粒/暗角合成、程序化 Web Audio 音乐与音效。

© 2026 SUNDOWN BAY MOTOR CLUB（虚构赛事品牌） · Independent procedural city kart game.
