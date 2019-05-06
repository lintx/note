不将虚拟机和真机的framework打包在一起，而是分开放置，然后自动连接的方式构思
1.scheme-edit-build-pre-actions中可以增加脚本，在每次编译前执行
2.该脚本可以使用$SDK_NAME变量获取目标sdk（使用虚拟机时，其中一个的值为iphonesimulator12.2，打包时，值为iphoneos12.2）
3.然后最简单的方法，就是判断sdkname，然后将sdk文件复制到某个目录，比如$(PROJECT_DIR)下某个文件夹

伪代码：
```
if sdk_name start with iohonesimulator
  cp -f project_dir/sdk/simulator/* project_dir/sdk/use
else
  cp -f project_dir/sdk/simulator/* project_dir/sdk/use
fi
```
等待测试完毕后再完善伪代码
