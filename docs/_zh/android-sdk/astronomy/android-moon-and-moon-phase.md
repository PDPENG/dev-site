---
title: 月升月落和月相
tag: [guide, android, astronomy, moon]
ref: 2-sdk-android-moon
---

获取未来60天全球城市月升月落和逐小时的月相数据。

> 月相已考虑南北半球的差异，不需要再进行转换

| 接口代码| 接口说明          | 数据类      |
| ------ | ---------- | ----------- |
| getMoon| 太阳和月亮数据  | MoonBean |

### 接口参数说明

{% include params.html p="location-android date60" %}

### 示例代码

```java
QWeather.getMoon(Context context, String location, String date, final OnResultMoonListener listener) ;

QWeather.getMoon(Context context, String location, Lang lang, String date, final OnResultMoonListener listener)                                
```

### MoonBean 属性

| 属性                 | 说明                       | 示例值                    |
| -------------------- | -------------------------- | ------------------------- |
| getCode              | 参考[状态码](/docs/resource/status-code/)                    | 200       |
| getRefer             | Refer 数据来源以及数据授权 | Refer                     |
| getMoonrise       | 当天[月升时间](/docs/resource/sun-moon-info/#moonrise-and-moonset)，**可能为空**                   | 2017-10-25T01:34+08:00           |
| getMoonset       | 当天[月落时间](/docs/resource/sun-moon-info/#moonrise-and-moonset)，**可能为空**                   | 2017-10-25T04:34+08:00           |
| getMoonPhaseBeanList | 月相信息                   | List\<MoonPhaseBean> |

**Refer**

| 属性           | 说明         | 示例值             |
| -------------- | ------------ | ------------------ |
| getSourcesList | 原始数据来源 | QWeather      |
| getLicenseList | 使用许可     | QWeather Developers License |

**Basic**

| 属性          | 说明                     | 示例值               |
| ------------- | ------------------------ | -------------------- |
| getUpdateTime | 接口更新时间             | 2017-10-25T04:34     |
| getFxLink     | 所查询城市的天气预报网页 | https://www.qweather.com/weather/beijing-101010100.html |


**MoonPhaseBean**

| 属性            | 说明                   | 示例值                 |
| --------------- | ---------------------- | ---------------------- |
| getFxTime       | 月相逐小时预报时间     | 2013-12-31T23:31+08:00 |
| getValue        | 月相数值               | 0.25                   |
| getName         | [月相名称](/docs/resource/sun-moon-info/#moon-phase)               | 上弦月                 |
| getIllumination | 月亮照明度，百分比数值 | 30                     |
| getIcon | 月相[图标代码](/docs/resource/icons/)，另请参考[天气图标项目](https://icons.qweather.com/) | 802                     |
