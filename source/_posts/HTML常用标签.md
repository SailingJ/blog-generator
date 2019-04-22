---
title: HTML常用标签
date: 2019-04-02 22:37:51
tags:
---
## <a标签>
HTML **a元素**（或称锚元素）可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。
```
1. <a href://http:qq.com></a>
   <a href://http:qq.com?xxx></a>
2. <a href://http:qq.com#xxx></a>
3. <a href:javascript:;></a>
```
其中**1**是链接到**外部地址**，**2**是链接到**本页的某部分**即不发出请求，3为**伪协议**，如弹出一个小窗口

## <form标签>
HTML **form** 元素 表示了文档中的一个区域，这个区域包含有交互控制元件，用来向web服务器提交信息。
其中from表单里一定要有提交按钮

## <input标签>
HTML **input** 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据; 可以使用各种类型的输入数据和控件小部件，具体取决于设备和user agent。
其中input标签可以用label关联
常用**radio**为单选框，**checkbox**为多选框
<small>input无子元素，button有子元素</small>

## <table标签>
HTML的 **table元素**表示表格数据 — 即通过二维数据表表示的信息。
形式上分为表头thead（th）、主题tbody（tb）、脚tfoot（tf），浏览器可以自动修正三者正确顺序
还有table row（tr），table data（td）
colgroup可定义一组列表
table 的 border 默认有空隙