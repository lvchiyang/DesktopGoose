# ��������Ӧ����Դ�����ĵ�

## 1. ���ϰ���������
### ����Ȩ��
```xml
<uses-permission android:name="android.permission.BIND_ACCESSIBILITY_SERVICE"/>
<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
<uses-permission android:name="android.permission.FOREGROUND_SERVICE"/>
```

### ��������ʾ��
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

## 2. ��Դ�����嵥
### ������Դ
- ֡���� (PNG����)
  - ��·������8֡@256x256
  - idle������4֡@256x256
- Spine���� (��ѡ)
  - �汾Ҫ��3.8.99

### ��Ƶ��Դ
- WAV��ʽ 44.1kHz/16bit
  - �Ų��� (3�ֱ���)
  - ������Ч (5��)

## 3. ϵͳҪ��
- ���Android�汾��7.0 (API 24)
- Ŀ��API����34
- �ڴ�ռ�����ƣ�<50MB

## 4. ��������
```groovy
implementation 'androidx.core:core-ktx:1.12.0'
implementation 'androidx.lifecycle:lifecycle-service:2.6.2'