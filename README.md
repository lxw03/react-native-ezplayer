# react-native-ezplayer
![License](https://img.shields.io/cocoapods/l/EZPlayer.svg?style=flat) [![NPM version][npm-image]][npm-url]

EZPlayer component for react-native apps

## 预览

![EZPlayerRNBase](EZPlayerRNBase.gif) ![EZPlayerRNList](EZPlayerRNList.gif)


## 介绍
基于EZPlayer(https://github.com/easyui/EZPlayer)封装的视频播放器，功能丰富，快速集成，可定制性强。


## 特性
- 本地视频、网络视频播放（支持的格式请参考苹果AVPlayer文档）
- [全屏模式/嵌入模式/浮动模式随意切换(支持根据设备自动旋转)](#DisplayMode)
- [全屏模式支持横屏全屏和竖屏全屏](#DisplayMode)
- [定制手势：播放/暂停(全屏/嵌入模式双击，浮动模式单击)，浮动和全屏切换（双击），音量/亮度调节（上下滑动），进度调节（左右滑动）](#GestureRecognizer)
- [支持airPlay](#airPlay)
- [支持UITableview自动管理嵌入和浮动模式切换](#tableview)
- [视频比例填充（videoGravity）切换](#videoGravity)
- [字幕/CC切换](#subtitle&cc&audio)
- [音频切换](#subtitle&cc&audio)
- [拖动进度显示预览图（m3u8不支持）](#preview)
- [播放器控件皮肤自定义（自带一套浮动皮肤，嵌入和全屏用的一套皮肤）](#skin)
- [支持广告功能](#ad)

## 使用
可以参考[EZPlayerExample_RN](https://github.com/easyui/EZPlayer/tree/master/EZPlayerExample_RN)项目，

## Properties


| key | description | value |                   
| --- | --- | --- | 
| source | 视频数据源  | PropTypes.object |
| autoPlay|设置数据源后自动播放| PropTypes.bool |
| useDefaultUI|使用EZPlayer自带皮肤| PropTypes.bool |
| videoGravity|视频画面比例| PropTypes.string(aspect,aspectFill,scaleFill) |
| fullScreenMode|全屏模式是竖屏还是横屏| PropTypes.string(portrait,landscape) |
| onPlayerHeartbeat|播放器声明周期心跳| PropTypes.func |
| onPlayerPlaybackTimeDidChange|addPeriodicTimeObserver方法的触发| PropTypes.func |
| onPlayerStatusDidChange|播放器状态改变| PropTypes.func |
| onPlayerPlaybackDidFinish|视频结束| PropTypes.func | 
| onPlayerLoadingDidChange|loading状态改变| PropTypes.func | 
| onPlayerControlsHiddenDidChange|播放器控制条隐藏显示| PropTypes.func | 
| onPlayerDisplayModeDidChange|播放器显示模式改变了（全屏，嵌入屏，浮动）| PropTypes.object | 
| onPlayerDisplayModeChangedWillAppear |播放器显示模式动画开始| PropTypes.func |
| onPlayerDisplayModeChangedDidAppear |播放器显示模式动画结束| PropTypes.func |
| onPlayerTapGestureRecognizer |点击播放器手势通知| PropTypes.func |
| onPlayerDidPersistContentKey |FairPlay DRM| PropTypes.func |


| function | description | value |                   
| --- | --- | --- | 
| play() | 播放  | PropTypes.object |
| pause() |暂停| PropTypes.bool |
| stop() |结束| PropTypes.bool |
| seek(time, callback) |设置播放进度，单位秒| PropTypes.string(aspect,aspectFill,scaleFill) |
| replaceToPlay(source) |替换播放源| PropTypes.string(portrait,landscape) |
| rate(rate) |设置播放速率| PropTypes.func |
| autoPlay(autoPlay) |设置自动播放，autoPlay是PropTypes.bool| PropTypes.func |
| videoGravity(videoGravity) |设置视频画面比例，| PropTypes.func |
| toEmbedded(animated = true, callback) |进入嵌入屏模式| PropTypes.func | 
| toFloat(animated = true, callback) |进入悬浮屏模式| PropTypes.func | 
| toFull(orientation = 'landscapeLeft', animated = true, callback) |进入全屏模式| PropTypes.func | 
| fullScreenMode(fullScreenMode)|播放器显示模式改变了（全屏，嵌入屏，浮动）| PropTypes.object | 
| onPlayerDisplayModeChangedWillAppear |播放器显示模式动画开始| PropTypes.func |
| onPlayerDisplayModeChangedDidAppear |播放器显示模式动画结束| PropTypes.func |
| onPlayerTapGestureRecognizer |点击播放器手势通知| PropTypes.func |
| onPlayerDidPersistContentKey |FairPlay DRM| PropTypes.func |



主要文件：

EZRNPlayerView.swift ： 对EZPlayer的封装

EZRNPlayerViewManager.swift ： EZPlayer组件管理器

EZRNPlayerViewBridge.h & EZRNPlayerViewBridge.m ： oc桥接

EZPlayer.js ： 对EZPlayer封装的js api

demo文件：
BasePlayerExample.js ： EZPlayer的基础功能演示
TablePlayerExample.js ：EZPlayer 在列表中的演示
TablePlayerCell.js ： 列表的cell
EZCustomPlayer.js ： 对EZPlayer.js进行封装，使用自定义ui，自定义ui可参考。
Utils.js ： 工具类

## Todo
- 支持VR
- 支持iPad pip
- 支持本地m3u8
- 支持多码率控制
- 支持3d touch截图，截图后简单处理
- 支持边缓存边下载
- 支持视频解密播放
- 支持tvOS
- 支持播放百分比触发
- 国际化
- 记忆播放
- 支持滤镜

## License
EZPlayer遵守MIT协议，具体请参考MIT








