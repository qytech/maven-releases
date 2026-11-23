# QYTech Android SDK

这是 QYTech Android SDK 的公开 Maven 仓库。通过 Gradle 添加依赖时无需 GitHub 账号或访问令牌。

## 通过 Gradle 接入

在项目根目录的 `settings.gradle.kts` 中，将 QYTech 仓库加入已有的 `dependencyResolutionManagement.repositories`。保留 `google()` 和 `mavenCentral()`，供 Gradle 解析 AndroidX 等传递依赖。

```kotlin
dependencyResolutionManagement {
    repositories {
        maven("https://qytech.github.io/maven-releases/") {
            content { includeGroup("io.github.qytech") }
        }
        google()
        mavenCentral()
    }
}
```

在使用 SDK 的模块的 `build.gradle.kts` 中，按需添加依赖。

```kotlin
dependencies {
    implementation("io.github.qytech:audioplayer:1.2.12")
    implementation("io.github.qytech:networkstorage:0.1.12")
    implementation("io.github.qytech:screenmirror:0.1.2")
    implementation("io.github.qytech:qymultiroom:0.0.5")
}
```

## 下载 AAR

| SDK | 用途 | 制品 | 校验值 |
| --- | --- | --- | --- |
| `audioplayer` | 音频播放 | [1.2.12 AAR](https://qytech.github.io/maven-releases/io/github/qytech/audioplayer/1.2.12/audioplayer-1.2.12.aar) | [SHA-256](https://qytech.github.io/maven-releases/io/github/qytech/audioplayer/1.2.12/audioplayer-1.2.12.aar.sha256) |
| `networkstorage` | SMB 和 NFS 网络存储访问 | [0.1.12 AAR](https://qytech.github.io/maven-releases/io/github/qytech/networkstorage/0.1.12/networkstorage-0.1.12.aar) | [SHA-256](https://qytech.github.io/maven-releases/io/github/qytech/networkstorage/0.1.12/networkstorage-0.1.12.aar.sha256) |
| `screenmirror` | 屏幕采集、投屏与远程输入 | [0.1.2 AAR](https://qytech.github.io/maven-releases/io/github/qytech/screenmirror/0.1.2/screenmirror-0.1.2.aar) | [SHA-256](https://qytech.github.io/maven-releases/io/github/qytech/screenmirror/0.1.2/screenmirror-0.1.2.aar.sha256) |
| `qymultiroom` | Android 多房间音频 SDK（ARM64） | [0.0.5 AAR](https://qytech.github.io/maven-releases/io/github/qytech/qymultiroom/0.0.5/qymultiroom-0.0.5.aar) | [SHA-256](https://qytech.github.io/maven-releases/io/github/qytech/qymultiroom/0.0.5/qymultiroom-0.0.5.aar.sha256) |

qymultiroom 的 Native 组件使用 FFmpeg、SACD Ripper 和 Snapcast 等开源软件。0.0.5 的对应源码包包含上游源码、QY Native 修改、补丁和重建脚本。[Native 源码下载](https://github.com/qytech/maven-releases/releases/download/qymultiroom-0.0.5/qymultiroom-0.0.5-native-sources.zip) · [组件许可证及源码校验值](https://qytech.github.io/maven-releases/io/github/qytech/qymultiroom/0.0.5/qymultiroom-0.0.5-notices.zip)
