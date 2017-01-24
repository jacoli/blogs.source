---
title: ObjectiveC杂项
date: 2015-04-06 23:07:56
comments: true
categories:
- 技术
- 移动开发
tags:
- iOS
---

### arc：
http://clang.llvm.org/docs/AutomaticReferenceCounting.html#bridged-casts

### Toll-Free-Bridging
http://gracelancy.com/blog/2014/04/21/toll-free-bridging/
(__bridge T) op：告诉编译器在 bridge 的时候不要做任何事情
(__bridge_retained T) op：（ ObjC 转 CF 的时候使用）告诉编译器在 bridge 的时候 retain 对象，开发者需要在CF一端负责释放对象
(__bridge_transfer T) op：（ CF 转 ObjC 的时候使用）告诉编译器转移 CF 对象的所有权，开发者不再需要在CF一端负责释放对象






