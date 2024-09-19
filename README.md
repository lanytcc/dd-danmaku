# fork改进
更改上游danmaku.js弹幕位置计算方式，解决滚动弹幕相互覆盖的问题

使用min.js，减少体积，加快加载速度

推荐nginx反向代理加载js，其他方式也是可以的
```nginx
sub_filter '</body>' '<script src="https://cdn.jsdelivr.net/gh/lanytcc/Danmaku@v1.1.0/dist/danmaku.min.js"></script> <script src="https://cdn.jsdelivr.net/gh/lanytcc/dd-danmaku@v1.0.0/ede.min.js" defer></script></body>';
sub_filter_once on;
```

使用uglifyjs压缩
```bash
uglifyjs ede.js -o ede.min.js -c
```