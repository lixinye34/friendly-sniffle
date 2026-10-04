# 李新叶第一中学 · 官网静态站点

李新叶第一中学（李新叶教育集团）官方网站静态源码，可直接部署到 GitHub Pages / Cloudflare Pages 等静态托管平台。

## 项目结构

```
lixinye-school/
├── index.html          # 网站首页（入口）
├── assets/             # 静态资源目录
│   ├── badge.png       # 校徽（推荐用学校正式校徽替换）
│   ├── badge.svg       # 校徽占位图（未放置 badge.png 时自动回退显示）
│   ├── hero.jpg        # 首页大图 Banner
│   ├── intro.jpg       # 学校概况配图（教学楼）
│   ├── campus-main.jpg # 主校区
│   ├── campus-yushi.jpg# 尉氏校区
│   ├── campus-mingde.jpg # 明德校区
│   ├── news1.jpg       # 新闻配图1
│   ├── news2.jpg       # 新闻配图2
│   └── video/          # 宣传片视频目录（放置 video1.mp4 / video2.mp4）
└── README.md           # 本说明
```

## 网站板块

- 学校概况 / 校徽识别 / 领导团队（校长君君豪、副校长陈瑞泽）
- 集团三大校区（主校区、尉氏校区、明德校区）
- 校园宣传片（双视频）
- 新闻中心 / 招生入学 / 历年招生政策 / 联系我们

## 部署到 Cloudflare Pages（推荐）

1. 将本文件夹推送到你的 GitHub 仓库（步骤见下）。
2. 登录 [Cloudflare](https://dash.cloudflare.com/) → Workers & Pages → Create → Pages → **Connect to Git**。
3. 授权选择刚才的仓库，Build 设置：
   - **Framework preset**：None
   - **Build command**：留空
   - **Build output directory**：`/`（或留空，默认读取 index.html）
4. 点击 **Save and Deploy**，等待部署完成。
5. 部署成功后获得默认域名 `xxx.pages.dev`（这就是网站公网访问地址，全世界任何手机/电脑可打开）。
6. 如需正式域名，在 Pages 项目 → Custom domains 绑定你自己的域名即可。

## 部署到 GitHub Pages

1. 把文件夹内容推送为 GitHub 仓库。
2. 仓库 → Settings → Pages → Source 选 `Deploy from a branch` → 分支选 `main`、目录选 `/ (root)`。
3. 保存后约 1 分钟，即可通过 `https://<用户名>.github.io/<仓库名>/` 访问。

## 如何更新历年招生政策

编辑 `index.html` 底部的 `POLICIES` 数组，添加一个新年度对象即可，历史年份自动保留：

```js
{
    year: "2027年",
    batch: "初中毕业生招生 · 秋季入学",
    items: [
        { k: "中考总分", v: "满分750分" },
        { k: "最低录取分数线", v: "XXX分" },
        { k: "招生范围", v: "面向全县应届初中毕业生" },
        { k: "报名渠道", v: "微信公众号 / 抖音 / 快手" }
    ],
    note: "本年度录取说明。"
}
```

## 替换校徽 / 视频

- 校徽：用学校正式校徽图片替换 `assets/badge.png`（建议正方形 PNG，透明底或白底）。
- 宣传片：把视频文件命名为 `video1.mp4`、`video2.mp4`，放入 `assets/video/` 目录即可自动播放。
