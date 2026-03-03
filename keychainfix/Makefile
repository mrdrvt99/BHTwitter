makefileTARGET := iphone:clang:latest:14.0   # ← you can keep 14.0 as min deployment (works on old devices too)
                                     #   or raise to 15.0 / 16.0 / 18.0 if you only care about newer iOS

# Add / change these lines to force using the downloaded 18.6 SDK
SDKVERSION             = 18.6
THEOS_DEVICE_SDK_VERSION = 18.6
SDKROOT                ?= $(THEOS)/sdks/iPhoneOS18.6.sdk

# Recommended for modern Theos + iOS 18 builds (arm64e is required on newer devices)
ARCHS                  = arm64 arm64e

INSTALL_TARGET_PROCESSES = Twitter   # ← fine, but note: app is now called "X" — if injecting into current X app, change to X (case-sensitive)

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = keychainfix
keychainfix_FILES = Tweak.x
keychainfix_FRAMEWORKS = UIKit Foundation Security
keychainfix_CFLAGS = -fobjc-arc

include $(THEOS_MAKE_PATH)/tweak.mk

