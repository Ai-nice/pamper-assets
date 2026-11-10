# pamper action assets

这是桌面宠物「发现」页使用的**预转换透明 WebM 动作库**（819 个动作，按 6 个动作包 / 4 个角色组织）。

## 目录约定

```
pets/<pack>/<action>.webm
```

例如：

```
pets/dsh/待机呼吸休闲.webm
pets/dsh1/工作加班.webm
pets/claude/OK手势.webm
```

`manifest.json` 记录了每个动作的大小；动作名与主仓库 `catalog/action-store.json` 的 `action.webm` 字段一致。

## 用途

主仓库（桌面宠物）的 Host 插件 `dsh-action-store` 会按 `assetBaseUrl + action.webm` 下载单个动作文件到本地缓存后安装，因此：

- 用户不需要下载整个 1.4 GB 素材库；
- 不需要 ffmpeg（文件已经是 alpha WebM）；
- 用过的动作才会占磁盘。

把本目录作为一个独立 GitHub 仓库上传后，可得到：

- jsDelivr（推荐，国内较快）：`https://cdn.jsdelivr.net/gh/Ai-nice/<仓库>@main`
- GitHub raw：`https://raw.githubusercontent.com/Ai-nice/<仓库>/main`

把该根地址填入主仓库 `plugin/dsh-action-store/cordis.patch.yml` 的 `assetBaseUrl`，重新安装插件即可。

## 素材来源与许可

动作素材来自 aboutme-pets（`https://github.com/hunmer/aboutme-pets`）及其记录的原始作者仓库；请保留各动作包内的 `NOTICE.txt`、`LICENSE-*.txt`、`SOURCE-upstream.txt` 等许可文件，并遵守相应许可证再分发。
