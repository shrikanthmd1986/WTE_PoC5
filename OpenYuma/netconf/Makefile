# Makefile for Yuma entire tools directory
#  
#   top directory

##################### LIBRARIES ########################
#
# DIRS:  
# This is an ordered list
# Put only the directories that build object files in the list

ifndef PREFIX
    PREFIX=/usr
endif

# make all targets
DIRS = src modules etc doc man util

TOP_INSTALL = $(DESTDIR)$(PREFIX)/share/yuma

#################### PLATFORM DEFINITIONS ############

all: treeall

################################ MAKE RULES #################################

clean: treeclean

superclean: treesuperclean

distclean: treedistclean

install: treeinstall

uninstall: treeuninstall

treeall:
	for dir in $(DIRS); do\
	  cd $$dir && $(MAKE) $(JFLAG) all && cd ..;\
        done

treeclean:
	for dir in $(DIRS); do\
	  cd $$dir && $(MAKE) clean && cd ..;\
        done

treesuperclean:
	for dir in $(DIRS); do\
	  cd $$dir && $(MAKE) superclean && cd ..;\
        done

treedistclean:
	for dir in $(DIRS); do\
	  cd $$dir && $(MAKE) distclean && cd ..;\
        done

treeinstall:
	mkdir -p $(TOP_INSTALL)
ifndef DEVELOPER
	mkdir -p $(TOP_INSTALL)/modules
endif
	for dir in $(DIRS); do\
          cd $$dir && $(MAKE) install && cd ..;\
        done


treeuninstall:
	for dir in $(DIRS); do\
          cd $$dir && $(MAKE) uninstall && cd ..;\
        done


.PHONY: all clean superclean distclean install uninstall \
	treeall treeclean treesuperclean treedistclean \
	treeinstall treeuninstall


# prevent the make program from choking on all the symbols
# that get generated from autogenerated make rules
.NOEXPORT:



