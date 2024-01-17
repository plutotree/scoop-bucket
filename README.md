[![Tests](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/ci.yml) [![Excavator](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/plutotree/scoop-bucket/actions/workflows/excavator.yml)

## Usage

After scoop has been installed, run the following:

```pwsh
scoop bucket add plutotree https://github.com/plutotree/scoop-bucket
scoop install plutotree/<manifestname>
```

## Manifests

| Name            | Desc                     | AppData              | AutoUpdate | AutoStop |
| --------------- | ------------------------ | ---------- | ---------- | ---------- |
| bookxnote-pro   | BookXNote Pro 电子书阅读 | ❌ | ✔️⭕️      |      |
| cos-browser     | 腾讯云 Cos 管理工具      | ️️✔️️ | ️️✔️️      |      |
| qqmusic | QQ音乐 | ❌ | ✔️⭕️ | |
| snipaste2       | Snipaste 截图            | ⛔️          | ️️✔️️      |      |
| tencent-meeting | 腾讯会议                 | ❌                | ️️✔️️      | ✔️️   |
| tencent-video | 腾讯视频 | ❌ | ✔️⭕️ |  |

- ✔️ Yes
- ❌ No
- 🛠 Additional testing is needed
- ⭕️ Hash calculated locally
- ⛔️
- ✋



- AutoUpdate: auto update manifest by GitHub actions
- AutoStop: auto stop process in uninstall script



## Notes

1. Tencent Meeting can only run in version directory, current directory doesn't work. Fortunately, the script has already fix the issue internally.
