# DiPlay  —— Android 8.1（API 27）兼容分支

这是 [shihabal3amri/DiPlay](https://github.com/shihabal3amri/DiPlay) 开源项目 **DiPlay** 的一个社区修改分支，目标是让应用在 **Android 8.1（API 27）车机**上也能安装并正常运行。

> ⚠️ **本分支非官方维护。** 上游官方最低支持版本为 Android 9（API 28）。本分支在 Android 8.1 上的运行未经上游验证，仅作者自用，请自行评估风险。

---

## 相对原版改了什么

| 文件                        | 修改                                                                           |
| ------------------------- | ---------------------------------------------------------------------------- |
| `mobile/build.gradle.kts` | `minSdk` 28 → **27**                                                         |
| `common/build.gradle.kts` | `minSdk` 28 → **27**                                                         |
| `shared/build.gradle`     | `minSdk` 28 → **27**；NDK 编译平台 `APP_PLATFORM` `android-28` → **`android-27`** |

源码中高版本 API（Android 9/10/11/13+）的调用都带有 `Build.VERSION.SDK_INT` 版本判断保护，在 Android 8.1 上会自动走兼容分支，只缺失依赖新系统的边缘功能，主体功能不受影响。

---

## 仓库里**不包含**什么（重要）

本仓库**只含源码**，不包含以下两类敏感/专有资产：

1. **CarPlay（MFi）认证凭据** `identity.pk8` / `certificate.p7b`
   —— 这是开发者专有资产，本分支默认构建**不含** CarPlay 认证。
2. **签名密钥**（`.jks` / `.keystore`）
   —— 每个发布者应使用自己的签名密钥。

---

## 免责声明

本分支由社区维护，与上游作者无关。CarPlay / MFi 认证涉及专有许可，请遵守 Apple MFi 与相关法律法规。使用本分支产生的任何后果由使用者自行承担。
