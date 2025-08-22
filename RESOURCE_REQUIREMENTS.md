# 桌面宠物鹅应用资源需求文档

## 1. 无障碍服务配置
### 必需权限
```xml
<uses-permission android:name="android.permission.BIND_ACCESSIBILITY_SERVICE"/>
<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
<uses-permission android:name="android.permission.FOREGROUND_SERVICE"/>
```

### 服务声明示例
```xml
<service
    android:name=".GooseAccessibilityService"
    android:permission="android.permission.BIND_ACCESSIBILITY_SERVICE">
    <intent-filter>
        <action android:name="android.accessibilityservice.AccessibilityService"/>
    </intent-filter>
    <meta-data
        android:name="android.accessibilityservice"
        android:resource="@xml/goose_service_config"/>
</service>
```

## 2. 资源需求清单
### 动画资源
- 帧动画 (PNG序列)
  - 走路动画：8帧@256x256
  - idle动画：4帧@256x256
- Spine动画 (可选)
  - 版本要求：3.8.99

### 音频资源
- WAV格式 44.1kHz/16bit
  - 脚步声 (3种变体)
  - 交互音效 (5种)

## 3. 系统要求
- 最低Android版本：7.0 (API 24)
- 目标API级别：34
- 内存占用限制：<50MB

## 4. 开发依赖
```groovy
implementation 'androidx.core:core-ktx:1.12.0'
implementation 'androidx.lifecycle:lifecycle-service:2.6.2'