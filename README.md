# 18+ 与纯 4K 站点订阅（FongMi / 影视TV）

只放两类东西：**18+ 采集站**（`type: 1` JSON 接口）和**纯 4K 站点**（`type: 3` + jar 蜘蛛）。与 `SikROo/huangguo-spider` 完全独立。

## 订阅地址

| 用途 | 地址 |
|---|---|
| 只要 18+（68 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v2/18plus.json` |
| 只要 4K（19 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v2/4k.json` |
| 全都要（87 站） | `https://cdn.jsdelivr.net/gh/SikROo/tv18-4k-sources@v2/all.json` |

## 4K 分类

4K 这 19 个站全部来自 `type: 3` 的 jar 蜘蛛（配置里的 `spider`），站点名前面加了标记：

| 标记 | 含义 | 站点 |
|---|---|---|
| ❤ | **不需要网盘**，直连播放 | 立播、Emby、Emby001 |
| ☁ | 走网盘（夸克 / UC / 115 等），要扫码登录，多半还要会员 | 花卷、玩偶、观影、七味、盘库、虎斑、木偶、多多、快影、蜡笔、闪电、剧透、原盘、蜗牛、盘迷、逸动 |

说明：

- **立播（LibVio）**：站点本身是直连 HLS，spider 里另挂了网盘 Tab，所以标 ❤。
- **Emby / Emby001**：Emby 是 HTTP 直出流、不经网盘，但需要你自己的 Emby 服务器（配置里 `embynumber: 0` 表示「我的服务器」，没配就是空的），所以标 ❤ 但可能没内容。
- 其余 16 个是 4K 网盘聚合，播放时要先在 App 里扫码登录网盘；夸克一般要 88VIP/SVIP，UC 和天翼云盘不需要会员。
- jar 是被加固过的（`classes.dex` + 加密 payload + `wexguard` 原生库），没法静态判断每个站的具体实现，上面的分类依据是站点定位 + 公开资料（玩偶 = 夸克网盘、LibVio = 直连站等）。**如果你在 App 里试出某个 ☁ 其实能直连，告诉我，我改成 ❤。**

## 18+ 部分

从公开的 uz / TVBox 成人源配置里收集，逐个请求 `{api}?ac=videolist&pg=1` 验证，只保留返回正常 JSON 的站点。

- 站点名带 **⭐** = 不挂 VPN 直连可用；不带 ⭐ = 需要挂 VPN。
- 当前 68 个站，其中 43 个带 ⭐。

## 来源

- [FXQ0412/tvbox-4k](https://github.com/FXQ0412/tvbox-4k) —— 4K 站点与 spider jar
- [daliwang001/uz-sources](https://github.com/daliwang001/uz-sources) —— uz 格式成人源
- [chinawiz/tvbox](https://github.com/chinawiz/tvbox) —— TVBox 成人站点配置
- [YYDS678/uzVideo](https://github.com/YYDS678/uzVideo) —— `video_sources_sese.json` 原始出处

## 注意

- 内容版权归各源站，本仓库只整理访问方式；
- 18+ 内容请自行确认所在地法律，不要传播。
