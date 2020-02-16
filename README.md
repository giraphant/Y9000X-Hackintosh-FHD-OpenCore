# Y9000X-Hackintosh-FHD-OpenCore

---

# EFI信息
* 配置:FHD / i7 9750H / 32G / RC500+PM981 / DW1820A
* Open Core引导（0.55版本）
* 支持10.15系统（更新到10.15.3）
* 加入DW1820a的device property驱动，可以支持apple watch自动解锁 
* 加入屏蔽PM981补丁

# 引导说明
由于用Clover引导常常出现进入Windows后无法驱动声卡的情况，因此更换为OpenCore引导。与此同时，OpenCore对Windows的引导支持不是很好（数次卡在Windows锁屏界面），因此采用rEFInd统一引导，开机后用rEFInd的图形化界面选择需要进入的系统。

# 前期准备
* **更换硬盘**：pm981a无法安装黑苹果，我添加了一块RC500。由于有pm981存在，系统非常不稳定随时死机重启。必须拆下三星的这块硬盘或者屏蔽这块硬盘。
* **更换网卡为`DW1820a`**：我按照[黑果小兵](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html)的教程对这块网卡做了屏蔽。
* 切换硬盘模式为 `AHCI`
* 关闭`secure boot`
# 工作
* 显示相关：显示 背光 硬件加速 睡眠 雷电转HDMI（机型需为14,1）
* 网络相关：wifi 蓝牙 handoff airdrop imessage(需要自己配置三码)
* 其他硬件：耳机 麦克风 摄像头 触控板全手势 电源管理 雷电接口转接U盘
# 不工作
* 扬声器
* FN热键
   * 可以使用系统组合键调节亮度、声音等
# 其他问题
* 如果加了驱动却不生效：终端输入`kextstat | grep -v com.apple`查看已加载驱动
* 如果不是使用DW1820A这块网卡的话，先进BIOS关闭无线网卡，进入系统了再更换驱动

# 参考链接
*  https://github.com/hsd815/Y9000X-4K-hackintosh
*  https://github.com/programbw/y9000x
*  https://github.com/WangRicky/Y9000X-HACKINTOSH
*  https://github.com/goofysun/y9000x-4k-macos
