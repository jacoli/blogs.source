---
title: tableview的性能优化思路
date: 2016-04-28
comments: true
categories:
- 技术
- 移动开发
tags:
- iOS
---

* height缓存，ios8对height的理解较ios7有所改变，认为height随时变化，对获取height的方法调用更频繁。
* cell的缓存。
* cell的content的缓存和异步加载。
* content渲染优化，不透明、无圆角等。
* cell的subviews的层次尽量少。
* image资源的提前解压。
* 减少刷新次数，尽量减少`reloadData`的调用，改用`insertRows`、`reloadRows`等。