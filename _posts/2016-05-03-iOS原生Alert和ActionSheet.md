---
title: iOS原生Alert和ActionSheet
date: 2016-05-03
comments: true
categories:
- 技术
- 移动开发
tags:
- iOS
---

* ![alert](/images/alert.png)

```
    UIAlertController *vc = [UIAlertController alertControllerWithTitle:@"alertTitle"
                                                                message:@"message"
                                                         preferredStyle:UIAlertControllerStyleAlert];
    [vc addAction:[UIAlertAction actionWithTitle:@"done"
                                           style:UIAlertActionStyleDefault
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [vc addAction:[UIAlertAction actionWithTitle:@"cancel"
                                           style:UIAlertActionStyleCancel
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [vc addAction:[UIAlertAction actionWithTitle:@"warning"
                                           style:UIAlertActionStyleDestructive
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [self presentViewController:vc animated:YES completion:nil];
```

* ![actionsheet](/images/actionsheet.png)

```
    UIAlertController *vc = [UIAlertController alertControllerWithTitle:@"alertTitle"
                                                                message:@"message"
                                                         preferredStyle:UIAlertControllerStyleActionSheet];
    [vc addAction:[UIAlertAction actionWithTitle:@"done"
                                           style:UIAlertActionStyleDefault
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [vc addAction:[UIAlertAction actionWithTitle:@"cancel"
                                           style:UIAlertActionStyleCancel
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [vc addAction:[UIAlertAction actionWithTitle:@"warning"
                                           style:UIAlertActionStyleDestructive
                                         handler:^(UIAlertAction * _Nonnull action) {
    }]];
    
    [self presentViewController:vc animated:YES completion:nil];
```






