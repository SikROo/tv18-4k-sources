# 18+ 与纯 4K 站点订阅（FongMi / 影视TV）

只放两类东西：**18+ 采集站**（`type: 1` JSON 接口）和**纯 4K 站点**（`type: 3` + jar 蜘蛛）。与 `SikROo/huangguo-spider` 完全独立。

## 订阅地址

| 用途 | 地址 |
|---|---|
| 只要 18+（68 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v1/18plus.json` |
| 只要 4K（19 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v1/4k.json` |
| 全都要（87 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v1/all.json` |

## 说明

**18+ 部分**：从公开的 uz / TVBox 成人源配置里收集，逐个请求 `{api}?ac=videolist&pg=1` 验证，只保留返回正常 JSON 的站点。

- 站点名带 **⭐** = 不挂 VPN 直连可用；不带 ⭐ = 需要挂 VPN。
- 当前 68 个站，其中 43 个带 ⭐。

**4K 部分**：`type: 3` 站点，依赖配置里的 `spider` jar（
`http://oss4liview.moji.com/...jpg;md5;8605...`，实测可下载，PK 头正常）。
这些站来自 [FXQ0412/tvbox-4k](https://github.com/FXQ0412/tvbox-4k) 的 4K 站点，已按名字里的「4K」筛过：花卷 / 玩偶 / 观影 / 七味 / 盘库 / 虎斑 / 木偶 / 多多 / 快影 / 蜡笔 / 闪电 / 剧透 / 立播 / 原盘 / 蜗牛 / 盘迷 / 逸动 / Emby 两个。

- 4K 站是网盘/直连混合线路，能不能播取决于对应网盘账号和线路状态；
- jar 来自第三方，如果哪天 404，4K 那部分会整体失效（18+ 不受影响）。

## 来源

- [FXQ0412/tvbox-4k](https://github.com/FXQ0412/tvbox-4k) —— 4K 站点与 spider jar
- [daliwang001/uz-sources](https://github.com/daliwang001/uz-sources) —— uz 格式成人源
- [chinawiz/tvbox](https://github.com/chinawiz/tvbox) —— TVBox 成人站点配置
- [YYDS678/uzVideo](https://github.com/YYDS678/uzVideo) —— `video_sources_sese.json` 原始出处

## 注意

- 内容版权归各源站，本仓库只整理访问方式；
- 18+ 内容请自行确认所在地法律，不要传播。
