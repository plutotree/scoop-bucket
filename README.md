[![Tests](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml)

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
| cos-browser     | 腾讯云 Cos 管理工具      | ️️✔️️   | ️️✔️️      |          |
| evernote        | Evernote                 | ❌      | ⭕️        |          |
| qqmusic         | QQ 音乐                  | ❌      | ⭕️        |          |
| snipaste2       | Snipaste 截图            | ⛔️     | ️️✔️️      |          |
| tencent-docs    | 腾讯文档                 | ❌      | ⭕️        |          |
| tencent-meeting | 腾讯会议                 | ❌      | ️️✔️️      | ✔️️      |
| tencent-video   | 腾讯视频                 | ❌      | ⭕️        |          |
| ths-yhb         | 同花顺远航版             | ❌      | ⭕️        |          |

- AppData
  - ⛔️ Not use `AppData`
  - ✔️ Yes, use persist directory
  - ❌ No，use default `AppData` path

- AutoUpdate
  - ✔️ Yes
  - ❌ No
  - ⭕️ Yes，but hash is calculated locally after download

- AutoStop：Automatically stop processes during removing process
  - ✔️ Yes

✔️ ❌ 🛠 ⭕️ ⛔️✋

- AutoUpdate: auto update manifest by GitHub actions
- AutoStop: auto stop process in uninstall script

## Notes

1. Tencent Meeting can only run in version directory, current directory doesn't work. Fortunately, the script has already fix the issue internally.

## How to add a new app

1. create app manifest, named `xx.json`, check [offical wiki](https://github.com/ScoopInstaller/Scoop/wiki/Creating-an-app-manifest).
2. local install test: `scoop install xx`
3. local update test: `.\bin\checkver.ps1 -app xx -u`
4. git add & commit, all things done!
