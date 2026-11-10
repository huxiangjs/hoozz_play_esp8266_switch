#
# This is a project Makefile. It is assumed the directory this Makefile resides in is a
# project subdirectory.
#

PROJECT_NAME := switch

#
# Build-time version info for tracking, printed to the serial log at
# startup by print_build_info() in main.c:
#   - git branch and short sha of this repo at build time
#   - "-dirty" marker when the working tree has uncommitted changes
# The macros are empty strings when git is not available at build time.
#
GIT_BRANCH := $(shell git rev-parse --abbrev-ref HEAD 2>/dev/null)
GIT_SHA    := $(shell git rev-parse --short HEAD 2>/dev/null)
GIT_STATUS := $(shell git status --porcelain 2>/dev/null)
ifneq ($(GIT_STATUS),)
GIT_DIRTY  := -dirty
else
GIT_DIRTY  :=
endif
EXTRA_CFLAGS += -DAPP_GIT_BRANCH=\"$(GIT_BRANCH)\" -DAPP_GIT_SHA=\"$(GIT_SHA)\" -DAPP_GIT_DIRTY=\"$(GIT_DIRTY)\"

include $(IDF_PATH)/make/project.mk

