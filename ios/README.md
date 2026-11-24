# CatPhotos Dist

CatPhotos 的 SideStore / LiveContainer / AltStore Classic **国内加速**分发源。

本仓库只放：

- `apps.json` — AltStore Source
- `icon.png` — 源与 App 图标
- GitHub Releases 上的未签名 `CatPhotos.ipa`

应用源码在 [Wszl/cat-photos](https://github.com/Wszl/cat-photos)。IPA 由 Codemagic 构建后自动推送到本仓。

## 添加 Source

在 SideStore 或 LiveContainer 中添加：

```text
https://gh-proxy.com/https://raw.githubusercontent.com/Wszl/cat-photos-dist/main/ios/apps.json
```

`downloadURL` 同样经 `https://gh-proxy.com/` 代理 GitHub Release，便于国内下载。

## 安装说明

1. 添加上述 Source 后安装 **CatPhotos**
2. IPA **未签名**，需用 SideStore / LiveContainer **本地重签**
3. 免费 Apple ID 证书约 7 天需在 SideStore 内 Refresh
4. 首次打开请授权「全部照片」与本地网络

## 代理失效时

公共镜像可能限流或换域名。届时把 `apps.json` 里所有

`https://gh-proxy.com/https://...`

的前缀换成可用镜像（或暂时去掉前缀直连 GitHub），再提交本仓即可。发布脚本里的常量 `PROXY_PREFIX` 也需同步修改。

## 安全提示

- 不要把 Apple ID 密码或签名证书提交到本仓
- 经第三方代理下载的 IPA，建议与 Release 页面文件大小核对
