图片加载显示以及缓存的 Google samples
---
默认 repository 中的图片地址不能显示, 我改成了干货集中营的图片地址(我知道你懂😸) 提交了

git clone https://github.com/chinalwb/android-DisplayingBitmaps.git

然后导入这个文件夹下的 Application 到 Android Studio 即可运行 (如果有弹窗询问, 点击取消即可)


这个实例代码中主要演示了

1. 异步加载 bitmap 并设置到 imageView
2. LruCache / DiskLruCache
3. 从 LruCache 中移除的 bitmap 的软引用, 方便 bitmap 的 reuse (BitmapFactory.Options.inBitmap, 条件是被复用的 bitmap 的尺寸要比应用到的目标 bitmap 大 -- API_LEVEL >= 19, 如果是 18,则必须相等)
4. RecyclingImageView 在 GridView 中的使用, 当 GridView 的 view 被重复使用时, 根据 imageView 的显示状态和缓存状态, 来决定是否对Bitmap 进行 recycle 的操作
5. Google Sample 原文提到, 建议使用 Glide 或 Picasso


Android DisplayingBitmaps Sample
===================================

Sample demonstrating how to load large bitmaps efficiently off the main UI thread,
caching bitmaps (both in memory and on disk), managing bitmap memory and displaying
bitmaps in UI elements such as ViewPager and ListView/GridView.

Introduction
------------

This is a sample application for the Android Training class [Displaying Bitmaps Efficiently][1].

It demonstrates how to load large bitmaps efficiently off the main UI thread, caching
bitmaps (both in memory and on disk), managing bitmap memory and displaying bitmaps
in UI elements such as ViewPager and ListView/GridView.

[1]: http://developer.android.com/training/displaying-bitmaps/

Pre-requisites
--------------

- Android SDK 27
- Android Build Tools v27.0.2
- Android Support Repository

Screenshots
-------------

<img src="screenshots/1-gridview.png" height="400" alt="Screenshot"/> <img src="screenshots/2-detail.png" height="400" alt="Screenshot"/> 

Getting Started
---------------

This sample uses the Gradle build system. To build this project, use the
"gradlew build" command or use "Import Project" in Android Studio.

Support
-------

- Google+ Community: https://plus.google.com/communities/105153134372062985968
- Stack Overflow: http://stackoverflow.com/questions/tagged/android

If you've found an error in this sample, please file an issue:
https://github.com/googlesamples/android-DisplayingBitmaps

Patches are encouraged, and may be submitted by forking this project and
submitting a pull request through GitHub. Please see CONTRIBUTING.md for more details.

License
-------

Copyright 2017 The Android Open Source Project, Inc.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.
