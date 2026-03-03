# For sideloaded: Keep deployment low for broad device compat, but SDK high for modern headers/symbols
TARGET := iphone:clang:latest:14.0   # 14.0 is fine; bump to 15.0/16.0 if you want stricter iOS 18+ only

# Enforce the downloaded 18.6 SDK (from xybp888 repo)
SDKVERSION             = 18.6
THEOS_DEVICE_SDK_VERSION = 18.6
SDKROOT                ?= $(THEOS)/sdks/iPhoneOS18.6.sdk

# Critical for iOS 18+ devices (A12+ pointer auth, arm64e binaries)
ARCHS                  = arm64 arm64e

# Process to inject into (Twitter/X app)
# If targeting current X app versions, change to: INSTALL_TARGET_PROCESSES = X
INSTALL_TARGET_PROCESSES = Twitter

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = keychainfix
keychainfix_FILES = Tweak.x
keychainfix_FRAMEWORKS = UIKit Foundation Security
keychainfix_CFLAGS = -fobjc-arc

# Optional: If you hit linking issues with newer clang, add these
# keychainfix_LDFLAGS += -Wl,-rpath,@loader_path/Frameworks   # for embedded frameworks if any

include $(THEOS_MAKE_PATH)/tweak.mk
