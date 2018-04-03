---
layout: post
title: Drawboard PDF 和 pdftk 的冲突问题
tag: 工具debug
---
最近发现，Surface 必备应用 Drawboard PDF 和 pdf 转换工具 pdftk 不太兼容，具体表现为：将用 Drawboard PDF 做过笔记的 pdf 用 pdftk 进行转换时会报错，错误信息如下：
> Unhandled Java Exception in create_output():
> java.lang.ClassCastException: pdftk.com.lowagie.text.pdf.PdfString cannot be cast to pdftk.com.lowagie.text.pdf.PdfName

已经尝试过的操作有：
- 合并 pdf : `pdftk in1.pdf in2.pdf cat output out1.pdf`
- 旋转 pdf : `pdftk in.pdf cat 1-endeast output out.pdf`

均报错。 

可能的原因为：Drawboard PDF 和 pdftk 所用的 java 库版本不符，某一个软件用了版本较老的库。

目前只有一个比较笨的解决方法：用 “打印成 pdf 文件” 功能（如 Windows 平台下自带的 *Microsoft Print to PDF*）将做过笔记的 pdf 处理一下，再运行 pdftk。测试结果无错。