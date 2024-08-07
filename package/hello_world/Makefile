# 引入头文件 rules.mk
include $(TOPDIR)/rules.mk

# 设置PKG_*变量
PKG_NAME:=hello_world
PKG_VERSION:=1.0
PKG_BUILD_DIR:= $(BUILD_DIR)/$(PKG_NAME)

# 引入头文件 package.mk
include $(INCLUDE_DIR)/package.mk

# 定义hello_world信息
define Package/hello_world
	SECTION:=base
	CATEGORY:=Utilities
	TITLE:=Hello world -prints a hello world message
endef

# 定义hello_world说明
define Package/hello_world/description
	If you can't figure out what this program does, you're probably
	brain-dead and need immediate medical attention.
endef

# 编译前的准备
define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

# 定义hello_world安装什么
define Package/hello_world/install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hello_world $(1)/bin/
endef

# hello_world脚本处理完毕，调用
$(eval $(call BuildPackage,hello_world))

