TARGET := iphone:clang:latest:15.0
SDKVERSION = 18.6
THEOS_DEVICE_SDK_VERSION = 18.6
SDKROOT ?= $(THEOS)/sdks/iPhoneOS18.6.sdk
ARCHS = arm64 arm64e
INSTALL_TARGET_PROCESSES = Twitter
include $(THEOS)/makefiles/common.mk

TWEAK_NAME = keychainfix
keychainfix_FILES = Tweak.x
keychainfix_FRAMEWORKS = UIKit Foundation Security
keychainfix_CFLAGS = -fobjc-arc
include $(THEOS_MAKE_PATH)/tweak.mk
