## 配置信息

- **CPU：** i7-13700KF（默频）
- **无线网卡：** BCM94352Z（直接替换主板上的AX211网卡）
- **内存：** 金百达 银爵 DDR5 6400CL32 32Gx2（手动超频）
- **显卡：** AMD公版6800 矿卡（免驱）
- **硬盘：** 致钛 TiPlus7100 1T SSD（TRIM正常，速度7450M拉满）
- **电源：** 美商海盗船 SF750 白金

***

## 完善情况

-  无线网卡为白果卡，蓝牙和WiFi正常驱动，支持隔空投送、通用控制、连续互通等，但是这张卡5G最高只能434Mbps，全网无解。
-  独显正常驱动，所有输出接口（3xDP，1xHDMI）均可使用，解码正常。
-  USB接口已经定制，包括后面板全部USB3与USB2接口、C口，前面板2个USB口，无线网卡蓝牙等，速率均正常。
-  声卡使用id为66，正常使用，开机与白苹果一样输出开机音效。
-  休眠唤醒正常（建议系统设置中关闭电源小憩，否则会时不时自动唤醒又休眠）
-  板载有线网口正常，内网测试可以跑满2.5G速率。
- 对于单盘想装双系统的小伙伴，BootCamp功能可以正常使用，跟白果相同体验。

⚠️ **特别注意：**

* 在4K高刷显示器下，使用DP接口需要关闭显示器的DSC功能，否则DP口可能会不正常（黑屏、刷新率最高100Hz等问题）这是MacOS系统本身的问题，目前只有M1之后的机型才能正常使用DSC，关闭后DP口可以正常使用4K120Hz10Bit输出（无法HDR）或是4K95Hz10Bit（可以使用HDR）；HDMI接口同样最高120Hz而且感觉画面有点糊？

* 使用12/13代CPU时，因为Intel官方已经砍掉AVX512指令集，不建议在OC配置中开启 **EnableVectorAcceleration**属性，尤其是带F的CPU型号，否则可能会出现开机/重启随机黑屏然后五国，报错如下：

  ```
  [3:0:0][PPLIB] Failed to send PPLIB IRI to Accelerator.
  ...
  Kernel Extensions in backtrace:
           com.apple.iokit.IOGraphicsFamily(597.0)[5ABF1ED9-18B9-3062-8621-5ED1B70959BD]@0xffffff7fa8c7b000->0xffffff7fa8ca9fff
              dependency: com.apple.iokit.IOPCIFamily(2.9)[9367C7B9-149B-329D-B085-39BC7D39EF03]@0xffffff8015859000->0xffffff8015888fff
           com.apple.kext.AMDRadeonX6000Framebuffer(4.0.9)[C4AE7C14-A015-374F-9FA6-5BBB16E599BD]@0xffffff7f9fe12000->0xffffff7fa009bfff
  ```

***

## BIOS设置

- 内置设备设置
  - VT-d - Enable
  - Above 4G decoding - Enable
- CPU设置：
  - 虚拟化 - Enable（默认为关闭，不开无法启动PD、VMware这类虚拟机）
  - CFG Lock - Disable

***

## 系统信息界面

![image-20230511211732074.png](https://s2.loli.net/2023/05/11/kgF8YAKswiLjnGT.png)

![82d28342b7736622c65422b2c7f7c72a_0.png](https://s2.loli.net/2023/05/11/45dSRynGkEZ98ui.png)