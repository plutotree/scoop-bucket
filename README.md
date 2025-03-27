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
| cherry-studio | Cherry Studio 大模型AI助手 | ❌ | Yes | |
| cos-browser     | 腾讯云 Cos 管理工具      | ️️✔️️   | ️️✔️️      |          |
| evernote        | Evernote                 | ❌      | ⭕️        |          |
| modern-csv | Modern CSV 查看工具 | ❌ | ✔️️ | |
| qqmusic         | QQ 音乐                  | ❌      | ⭕️        |          |
| snipaste2       | Snipaste 截图            | ⛔️     | ️️✔️️      |          |
| tencent-docs    | 腾讯文档                 | ❌      | ⭕️        |          |
| tencent-meeting | 腾讯会议                 | ❌      | ️️✔️️      | ✔️️      |
| tencent-video   | 腾讯视频                 | ❌      | ⭕️        |          |
| tencent-yuanbao | 腾讯元宝 | ❌ | ❓ | |
| ths-yhb         | 同花顺远航版             | ❌      | ⭕️        |          |
| modern-csv      | Modern Csv             | ⛔️      | ⭕️        |          |
| en-croissant      | En Croissant             | ❌      | ⭕️        |          |
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

> `腾讯元宝 ` 无法找到合适的办法在非登录态获取版本号及最新的下载地址。官网支持匿名状态下“登录”流程，但是相关逻辑细节较复杂。目前的实现方式，需要依赖cookie信息，可以用匿名后的cookie信息，比如开启一个隐私窗口，打开"https://yuanbao.tencent.com" 后，将cookie结果保存在下述的环境变量中即可正常运行，GitHub Actions运行的时候也会指定cookie。
> `COOKIE_YUANBAO_TENCENT_COM`
>
> （如果谁梳理清楚了匿名登录的流程可以反馈下）



✔️ ❌ 🛠 ⭕️❓

## Notes

1. Tencent Meeting can only run in version directory, current directory doesn't work. Fortunately, the script has already fix the issue internally.

## How to add a new app

1. create app manifest, named `xx.json`, check [offical wiki](https://github.com/ScoopInstaller/Scoop/wiki/Creating-an-app-manifest).
2. local install test: `scoop install xx`
3. local update test: `.\bin\checkver.ps1 -app xx -u`
4. git add & commit, all things done!
