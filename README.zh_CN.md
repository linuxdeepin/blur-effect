离屏图像模糊工具
===

基于 [idea](http://rastergrid.com/blog/2010/09/efficient-gaussian-blur-with-linear-sampling/)

基于 debian/ubuntu
===
依赖:
+ libglm-dev
+ libglfw3-dev (仅在构建演示文件 `blur-exp` 时需要)
+ libglew-dev
+ libgbm-dev
+ libegl1-mesa-dev
+ libgles2-mesa-dev
+ libgdk-pixbuf2.0-dev

`mkdir build && cd build && cmake .. && make`

构建完成后，
使用二进制“blur_image”模糊图像并保存为文件。 通过 ./blur_image -h 显示用法
   示例：`./blur_image -p 10 -r 11 /usr/share/wallpapers/deepin/Garden\ In\ The\ Autumn.jpg -o out.jpg `

注意：如果您在运行 X 服务器的情况下运行它（这是最有可能的情况），请在前面添加 `sudo`。
或者您也可以使用render节点进行模糊处理而无需特权，例如：
```
./blur_image -d /dev/dri/renderD128 -p 6 -r 7 /usr/share/wallpapers/deepin/Garden\ In\ The\ Autumn.jpg -o out.jpg 
```

如果你想构建演示
使用 `cmake -DBUILD_DEMO=on ..` 指令代替，在构建完成后，
使用 `blur-exps` 测试窗口系统的模糊。


## License

此项目已获得 [GPLv3](LICENSE) 或任何更高版本的许可。

