# Makefile for decompiling devicetree binaries
# mew@mew.cx 2026-01-05

SHELL = /bin/sh

DTC = /usr/bin/dtc
DECOMPILE = $(DTC) --in-format dtb --out-format dts --sort

SRCS := $(wildcard *.dtbo)
TGTS := dtc_version.txt $(SRCS:.dtbo=.dts)

all : $(TGTS)

dtc_version.txt :
	$(DTC) --version >$@ 2>&1

%.dts : %.dtbo Makefile
	$(DECOMPILE) $< >$@ 2>&1

.SUFFIXES :

.PHONEY : clean clobber nuke
clean clobber nuke :
	-$(RM) $(TGTS)

# vim: set ts=8 noet ic ai:
