# oneko
> KimJungWha 的 feeds 仓库  
> 此仓库收集了一些网络上个人喜欢的软件，适用于 OpenWrt 主线版本
### 如何使用
在 OpenWrt 源码根目录下 feeds 文件中添加此仓库地址

	echo "src-git https://github.com/KimJungWha/oneko" >> feeds.conf.default

更新并创建源码的软链接

	./scripts/feeds update -a
	./scripts/feeds install -a



### 软件包内容
1. 主题相关
	* luci-theme-argon
	* luci-app-argon-config

2. ssr plus 全套依赖
	* v2ray 和 xray
	* trojan
	* 以及其他各项依赖

3. NAS (文件共享/文件下载) 相关
	* luci-app-nfs
	* luci-app-samba4

4. 网络相关
	* luci-app-nft-qos
	* luci-app-syncdial
	* luci-app-mwan3
	* luci-app-sfe
	* fast-classifier
	* shortcut-fe

5. 管理工具
	* luci-app-serverchan
6. 独家秘制的 [default-settings](https://github.com/KimJungWha/default-settings)
