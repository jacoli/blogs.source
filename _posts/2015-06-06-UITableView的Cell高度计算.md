---
title: UITableView的Cell高度计算
date: 2015-06-06 20:07:56
comments: true
categories:
- 技术
- 移动开发
tags:
- iOS
---
iOS7和iOS8有所区别，iOS7在需要调整布局时，计算一遍高度信息，而iOS8只要重新显示就会计算高度（iOS8 把高度计算搞成这个样子，从 WWDC 也倒是能找到点解释，cell 被认为随时都可能改变高度（如从设置中调整动态字体大小），所以每次滑动出来后都要重新计算高度。
 ）

iOS7:
1)获取section数和每个section中的row数
2)获取所有cell的高度，计算出tableView的contentSize
3)按已经算好的frame显示cell

iOS8:

1)获取section数和每个section中的row数
2)获取所有cell的高度，计算出tableView的contentSize（iOS8中该步骤调用更频繁）
3)重新获取当前需要显示cell的高度，调整tableView的contentSize，显示cell

UITableView的Cell高度计算＋估算

如果估算，则2）步骤中计算所有cell的高度改成估算所有cell的高度

```
    // All methods that trigger height cache's invalidation

    SEL selectors[] = {

        @selector(reloadData),

        @selector(insertSections:withRowAnimation:),

        @selector(deleteSections:withRowAnimation:),

        @selector(reloadSections:withRowAnimation:),

        @selector(moveSection:toSection:),

        @selector(insertRowsAtIndexPaths:withRowAnimation:),

        @selector(deleteRowsAtIndexPaths:withRowAnimation:),

        @selector(reloadRowsAtIndexPaths:withRowAnimation:),

        @selector(moveRowAtIndexPath:toIndexPath:)

    };

    

    for (NSUInteger index = 0; index < sizeof(selectors) / sizeof(SEL); ++index) {

        SEL originalSelector = selectors[index];

        SEL swizzledSelector = NSSelectorFromString([@"fd_" stringByAppendingString:NSStringFromSelector(originalSelector)]);

        

        Method originalMethod = class_getInstanceMethod(self, originalSelector);

        Method swizzledMethod = class_getInstanceMethod(self, swizzledSelector);

        

        method_exchangeImplementations(originalMethod, swizzledMethod);

    }
 ```