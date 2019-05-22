编译方法
===============
安装依赖库
--------
ubuntu系统下执行：

	apt-get install \
		bc \
		bison \
		bzip2 \
		ccache \
		cmake \
		curl \
		device-tree-compiler \
		dh-autoreconf \
		diffutils \
		doxygen \
		flex \
		g++ \
		gawk \
		gcc \
		git \
		gnat \
		graphviz \
		libcrypto++-dev \
		libfreetype6-dev \
		libftdi-dev \
		libftdi1-dev \
		libglib2.0-dev \
		libgmp-dev \
		libjaylink-dev \
		liblzma-dev \
		libncurses5-dev \
		libpci-dev \
		libreadline-dev \
		libssl-dev \
		libusb-1.0-0-dev \
		libusb-dev \
		libxml2-dev \
		libyaml-dev \
		m4 \
		make \
		msitools \
		nasm \
		openssl \
		patch \
		pkg-config \
		python \
		qemu \
		rsync \
		shellcheck \
		subversion \
		unifont \
		uuid-dev \
		vim-common \
		wget \
		xz-utils \
		zlib1g-dev

准备目标结构
--------
将vboot代码放置在coreboot/3rdparty/vboot, depthcharge解压后放在coreboot/payloads/external/depthcharge。

配置config文件
--------
**make nconfig**  
配置配置项，按F6保存配置后将在coreboot目录下生成.config文件。

编译交叉编译器
--------
**make crossgcc-arm**  
将会编译arm的交叉编译器，如果直接make crossgcc会编译各个平台的编译器时间太长。

编译rom文件
--------
**make -j16**  
编译完成后将在coreboot/build目录下生成coreboot.rom文件。这个文件即可使用flashrom工具输入设备的flash中。
刷flash方式参考《UPDATEBIOS.md》。
