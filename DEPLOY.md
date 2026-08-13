# 部署 frontend-lab

单文件静态站,无需构建。双部署:GitHub Pages(海外/VPN)+ Vercel(国内直连)。

## 现状:GitHub Pages(已上线)
画廊与各 demo 直接从 main 根目录服务,免构建:

- 画廊:https://fe-ng.github.io/frontend-lab/
- 01–07:在画廊下 `/01-aurora-parallax/` … `/07-view-transitions/`

> 国内访问 github.io 常断流,所以下面 Vercel 是国内备用主链路。

---

## Vercel(国内可直连,需你一次认证)

仓库已含 `vercel.json`(cleanUrls + 缓存头),零配置即可服务静态。三选一:

### A. dashboard 一键 connect(推荐,永久自动部署)
1. https://vercel.com → 登录 → New Project
2. Import `FE-ng/frontend-lab`
3. Framework Preset 选 "Other",Build Command / Output 留空(Vercel 自动识别静态)
4. Deploy → 得到 `https://frontend-lab-xxx.vercel.app`
5. 以后每次 `git push` 自动重新部署,无需任何操作

### B. Vercel CLI(我装好了,你只需 login 一次)
```bash
vercel login              # 浏览器授权一次
cd ~/frontend-lab
vercel --prod --yes       # 部署生产,首次会自动建项目
```
之后每次更新:`git push` 后再跑 `vercel --prod --yes`(非自动)。

### C. Token 部署(不开浏览器)
1. https://vercel.com 账号设置 → Tokens → 生成一个
2. `cd ~/frontend-lab && vercel --prod --yes --token=你的TOKEN`

---

## Vercel 上线后:把链接写进画廊首页
在 `index.html` 的 `.links` 区加一行:
```html
<a href="https://你的.vercel.app">Vercel(国内) ↗</a>
```
`git push` 即两处同时更新。

## 仓库(双源)
- https://github.com/FE-ng/frontend-lab
- 远程用 SSH(`git@github.com`),因 gh token 缺 workflow scope(本仓暂无 workflow,但保持 SSH 一致)
