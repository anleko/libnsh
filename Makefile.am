ACLOCAL_AMFLAGS = -I m4
doc_DATA        = LICENSE ChangeLog.md README.md
EXTRA_DIST      = LICENSE ChangeLog.md README.md autogen.sh
pkgconfigdir    = $(libdir)/pkgconfig
pkgconfig_DATA  = libnsh.pc
EXAMPLES        =
if ENABLE_EXAMPLES
  EXAMPLES     += examples
endif
SUBDIRS         = src $(EXAMPLES) tests

# Generate MD5 checksum file
MD5 = md5sum
md5-dist:
	@for file in $(DIST_ARCHIVES); do	\
		$(MD5) $$file > $$file.md5;	\
	done

# Target to run when building a release
release: dist md5-dist
	@for file in $(DIST_ARCHIVES); do				\
		printf "$$file    \tDistribution tarball\n";		\
		printf "$$file.md5\t"; cat $$file.md5 | cut -f1 -d' ';	\
	done
