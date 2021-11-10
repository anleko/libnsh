ACLOCAL_AMFLAGS = -I m4
doc_DATA        = LICENSE ChangeLog.md README.md
EXTRA_DIST      = LICENSE ChangeLog.md README.md autogen.sh
pkgconfigdir    = $(libdir)/pkgconfig
pkgconfig_DATA  = libnsh.pc
EXAMPLES        =
if ENABLE_EXAMPLES
  EXAMPLES     += examples
endif
SUBDIRS         = src $(EXAMPLES) test

# Target to run when building a release
release: distcheck
	@for file in $(DIST_ARCHIVES); do		\
		md5sum    $$file > ../$$file.md5;	\
		sha256sum $$file > ../$$file.sha256;	\
	done
	@mv $(DIST_ARCHIVES) ../
	@echo
	@echo "Resulting release files ======================================================================="
	@for file in $(DIST_ARCHIVES); do						\
		printf "%-30s Distribution tarball\n" $$file;				\
		printf "%-30s " $$file.md5;    cat ../$$file.md5    | cut -f1 -d' ';	\
		printf "%-30s " $$file.sha256; cat ../$$file.sha256 | cut -f1 -d' ';	\
	done
