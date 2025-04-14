# fnOS

admin@Dell-E7250:~$ cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 12 (bookworm)"
NAME="Debian GNU/Linux"
VERSION_ID="12"
VERSION="12 (bookworm)"
VERSION_CODENAME=bookworm
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
admin@Dell-E7250:~$

fnOS是基于Debian平台，

Debian 使用 systemd 管理电源事件。​您可以通过编辑 /etc/systemd/logind.conf 文件来配置合盖行为：​

打开终端，使用文本编辑器（如 nano）编辑该文件：


sudo nano /etc/systemd/logind.conf
找到以下两行（如果被注释，即行首有 #，请取消注释）：​

HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
如果这两行不存在，请添加到文件中。

保存并关闭文件。

重新启动 systemd-logind 服务以使更改生效：

sudo systemctl restart systemd-logind
这样设置后，无论在电池供电还是外接电源时，合上笔记本盖子都不会触发休眠。​
