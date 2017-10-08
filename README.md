# 9550-High-Sierra
>本项目不是安装教程，是我个人配置的完善，揉和了很多大神的成果。安装请参考 [darkhandz/XPS15-9550-High-Sierra](https://github.com/darkhandz/XPS15-9550-High-Sierra)，我也是参考他的教程，当然连带要感谢的人很多，包括 Rehabman, syscl, wmchris，corenel等。

#### 配置：
- 6700hq
- sm951 512GB SSD
- 16GB RAM
- 4K Display
- DW1830

目前是 `X86PlatformPluginInjector.kext` 需要手动装一下，声卡驱动需要手动添加一些配置，其它的基本都在 `Clover` 里。
蓝牙驱动通过往 `FakeSMC` 添加 `info` 配置来修改 `id` 驱动的，没有用 Rehabman 的驱动。


### 安装过程有几个可能需要注意的地方：
1. 删除 `EmuVariableUefi-64.efi` 驱动，完毕后可以再加回来（目前没有发现没有它会怎么样，反正亮度还是不能保存）。
2. 用最新的 `Clover Configurator` 更新 `SMBIOS` 信息，会自动帮你生成固件信息。
3. 如果之前 `Clover` 里有 `HibernationFixup.kext` 这个驱动，也请删除它，会导致出现 `slide` 计算正确依然报错的 bug。
4. `FakePCIID_Broadcom_WIFI.kext` 和 `AirportBrcmFixup` 不要一起用，会出现无限重启现象
5. 如果发现启动速度奇慢，可以看看 `FakePCIID.kext` 和 `FakePCIID_Intel_HDMI_Audio.kext` 有没有添加
6. `Clover` 里勾选 `FixHeaders_20000000`, 可以解决一个错误（我忘记什么错误了）
7. 论坛有个说将 `ig-platform-id` 改为 `0x19120000`, 可以驱动 `HDMI` 音频的，改完我就起不来了。
8. 碰到 `fs_get_inode` 什么的那个报错，更新一下 `apfs.efi`, 它藏在官方更新 App 的`BaseSystem.dmg` 镜像的 `/usr/standalone/i386/apfs.efi`。找不到可以先用本项目的。



