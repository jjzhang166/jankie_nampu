# Makefile for h264pack
#

EXCLUDE_DIRS := include lib

DIRS := ${shell find . -maxdepth 1 -type d}
DIRS := ${basename ${patsubst ./%, %, ${DIRS}}}
DIRS := ${filter-out ${EXCLUDE_DIRS}, ${DIRS}}

SUB_DIRS	:= ${DIRS}
CLEAN_DIRS 	:= $(addprefix _cls_, $(SUB_DIRS))

.PHONY: all clean ${SUB_DIRS} install uninstall

all: ${SUB_DIRS}

${SUB_DIRS}:
	${MAKE} -C $@

clean: ${CLEAN_DIRS}

${CLEAN_DIRS}: 
	${MAKE} -C $(patsubst _cls_%, %, $@) clean

install:
	${MAKE} -C ./src install

uninstall:
	${MAKE} -C ./src uninstall
