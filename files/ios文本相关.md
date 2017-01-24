### iOS文本相关

* 1、文字布局
* 2、Label、TextView、TextField、WebView等基础控件
* 3、键盘处理
* 4、自定义键盘
* 5、Copy、Cut、Paste操作、Menu
* 6、UIKit->TextKit->CoreText->Core Graphics
* 7、使用TextKit管理和绘制文本
* 8、UIKit中使用UIStringDrawing绘制文本
* 9、正则匹配

      // finds phone number in format nnn-nnn-nnnn
      NSRange r;
      NSString *regEx = @"[0-9]{3}-[0-9]{3}-[0-9]{4}";
      r = [textView.text rangeOfString:regEx  options:NSRegularExpressionSearch];
      if (r.location != NSNotFound) {
          NSLog(@"Phone number is %@", [textView.text substringWithRange:r]);
      } else {
          NSLog(@"Not found.");
      }

参考文档：Text Programming Guide for iOS