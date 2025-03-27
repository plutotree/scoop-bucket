[![Tests](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml)

## Disclaimer

This repository primarily serves as **personal usage**. If a software is later ​adopted by its official repository or ​no longer utilized in my workflow, it may be ​**removed** from this bucket without prior notice.

## Usage

After scoop has been installed, run the following:

```pwsh
scoop bucket add plutotree https://github.com/plutotree/scoop-bucket
scoop install plutotree/<manifestname>
```

## Manifests

| Name            | Desc                     | AppData | AutoUpdate | AutoStop |
| --------------- | ------------------------ | ------- | ---------- | -------- |
| bookxnote-pro   | BookXNote Pro 电子书阅读 | ❌      | ⭕️        |          |
| cherry-studio | Cherry Studio 大模型AI助手 | ❌ | Yes | |
| cos-browser     | 腾讯云 Cos 管理工具      | ️️✔️️   | ️️✔️️      |          |
| en-croissant      | En Croissant             | ❌      | ⭕️        |          |
| evernote        | Evernote                 | ❌      | ⭕️        |          |
| modern-csv | Modern CSV 查看工具 | ❌ | ✔️️ | |
| qqmusic         | QQ 音乐                  | ❌      | ⭕️        |          |
| snipaste2       | Snipaste 截图            | ⛔️     | ️️✔️️      |          |
| tencent-docs    | 腾讯文档                 | ❌      | ⭕️        |          |
| tencent-meeting | 腾讯会议                 | ❌      | ️️✔️️      | ✔️️      |
| tencent-video   | 腾讯视频                 | ❌      | ⭕️        |          |
| tencent-yuanbao | 腾讯元宝 | ❌ | ❓ | |
| ths-yhb         | 同花顺远航版             | ❌      | ⭕️        |          |
| windows-11-context-menu-manager | Windows 11 Context Menu Manager | ⛔️ | ⭕️ | |

- AppData
  - ⛔️ Not use `AppData`
  - ✔️ Yes, use persist directory
  - ❌ No，use default `AppData` path

- AutoUpdate: auto update manifest by GitHub actions
  - ✔️ Yes
  - ❌ No
  - ⭕️ Yes，but hash is calculated locally after download
  - ❓special problem

- AutoStop：Automatically stop processes during removing process
  - ✔️ Yes

✔️ ❌ 🛠 ⭕️❓

## Notes

1. Tencent Meeting can only run in version directory, current directory doesn't work. Fortunately, the script has already fix the issue internally.
2. Tencent Yuanbao: No reliable method has found to fetch the version number or latest download URL without authentication. While the official website supports an anonymous "login" flow, the underlying logic is complex. The current implementation relies on cookie data.
   You can use anonymized cookies (e.g., open a private/incognito window, visit https://yuanbao.tencent.com, then save the resulting cookies to the environment variable below) to run the workflow. GitHub Actions will also require specifying this cookie during execution: `COOKIE_YUANBAO_TENCENT_COM`
   (If anyone clarifies the anonymous login workflow, please share feedback.)

## Changelog

- 2025-03-27: Remove `siyuan-note`, as it has been maintained in offical [extras](https://github.com/ScoopInstaller/Extras/blob/master/bucket/siyuan-note.json)
- 2025-03-27: New add `tencent-yuanbao`

## How to add a new app

1. create app manifest, named `xx.json`, check [offical wiki](https://github.com/ScoopInstaller/Scoop/wiki/Creating-an-app-manifest).
2. local install test: `scoop install xx`
3. local update test: `.\bin\checkver.ps1 -app xx -u`
4. git add & commit, all things done!
