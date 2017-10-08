使用方法：
1.复制 AppleCALC.kext 到 CLOVER/kexts/Other
2.复制 VerbStub.kext 到 CLOVER/kexts/Other
2.确认一下 SSDT-Config.aml 中以下行的值是不是 0x48，可以参考本目录的，其它值不必求同。
```
        Name (AUDL, 0x48)
```
3.删除 CodecCommander.kext
4.执行 install.sh

说明:
- AppleALC.kext 是可以去官网更新的，驱动有问题的可以更新一下
- VerbStub.kext 目前还没有更新
- 驱动个人喜欢放到 Clover 里，你也可以选择放在 LE 下

以上文件来自于[wmchris/DellXPS15-9550-OSX](https://github.com/wmchris/DellXPS15-9550-OSX)，有改动，表示感谢。
跟进驱动动态可以到[原作者论坛帖子](http://www.insanelymac.com/forum/topic/324366-dell-xps-15-9560-4k-touch-1tb-ssd-32gb-ram-100-adobergb%E2%80%8B/page-6)
