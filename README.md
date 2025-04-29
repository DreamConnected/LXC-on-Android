# LXC-on-Android
> 推荐将 Release 下载解压到`/data/lxc`目录下，配置基本环境和安装工具如`busybox,getopt,xz`等等，这些并不包含在 LXC 项目中。
> 
> It is recommended to unzip the Release download to the `/data/lxc`, configure the basic environment and install tools such as `busybox,getopt,xz` and so on are not included in the LXC project.
>
> 对于GKI内核，请谨慎编译docker/lxc，他可能会导致你的设备无法启动。
>
> For the GKI kernel, please compile Docker/lxc with caution as it may cause your device to fail to start.
>

> [!WARNING]
> 
> THIS PROJECT IS NOT MAINTAINED ANYMORE.
> 
> PLEASE GO TO [Container-On-Android/lxc](https://github.com/Container-On-Android/lxc).

# LXC-6.0.0-Dev
|                  |  NDK  |  GNU  |  MUSL  |
|------------------|-------|-------|--------|
| start            |  [1]  |       |        |
| stop             |   √   |       |        |
| apparmor-load    |   ?   |       |        |
| containers       |   ?   |       |        |
| ls               |   √   |       |        |
| top              |   √   |       |        |
| attach           |  [2]  |       |        |
| copy             |   ?   |       |        |
| monitor          |   ×   |       |        |
| freeze/unfreeze  |   √   |       |        |
| autostart        |  [3]  |       |        |
| create           |  [4]  |       |        |
| monitord         |   ×   |       |        |
| unshare          |   ?   |       |        |
| cgroup           |   ?   |       |        |
| destroy          |   √   |       |        |
| net              |   √   |       |        |
| update-config    |   √   |       |        |
| checkconfig      |   √   |       |        |
| device           |   ?   |       |        |
| user-nic         |   ?   |       |        |
| checkpoint       |   √   |       |        |
| execute          |   ?   |       |        |
| snapshot         |  [5]  |       |        |
| usernsexec       |   ?   |       |        |
| config           |   √   |       |        |
| wait             |   ?   |       |        |
| console          |   √   |       |        |
| info             |   √   |       |        |

- [1] 需要在 share/lxc/config/common.conf 中注释/删除有关 tty,capabiities,seccomp 的配置，即第 10,13,82 行。
- [2] 需要在终端变量 LD_LIBRARY_PATH 中插入 lib 。
- [3] 需要在 lib/lxc/{container_name}/config 中添加 lxc.start.auto = 1 配置来开启容器自启。同时确保 lxc-autostart 拥有开机自启项。
- [4] 需要来自 GNU 的标准的 curl/wget/tar/xz 二进制,来自 busybox/toybox 等可能无法解析某些命令行操作。
- [5] 快照依赖于 copy 和其他组件，你需要确保其他组件能够正常工作。 

# LXC-5.0.0-Stable
|                  |  NDK  |  GNU  |  MUSL  |
|------------------|-------|-------|--------|
| start            |       |       |        |
| stop             |       |       |        |
| apparmor-load    |       |       |        |
| containers       |       |       |        |
| ls               |       |       |        |
| top              |       |       |        |
| attach           |       |       |        |
| copy             |       |       |        |
| monitor          |       |       |        |
| freeze/unfreeze  |       |       |        |
| autostart        |       |       |        |
| create           |       |       |        |
| monitord         |       |       |        |
| unshare          |       |       |        |
| cgroup           |       |       |        |
| destroy          |       |       |        |
| net              |       |       |        |
| update-config    |       |       |        |
| checkconfig      |       |       |        |
| device           |       |       |        |
| user-nic         |       |       |        |
| checkpoint       |       |       |        |
| execute          |       |       |        |
| snapshot         |       |       |        |
| usernsexec       |       |       |        |
| config           |       |       |        |
| wait             |       |       |        |
| console          |       |       |        |
| info             |       |       |        |
