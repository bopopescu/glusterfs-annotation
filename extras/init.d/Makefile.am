
EXTRA_DIST = glusterd-Debian glusterd-FreeBSD glusterd-Redhat glusterd-SuSE glusterd.plist rhel5-load-fuse.modules

CLEANFILES =

INIT_DIR = @initdir@
SYSTEMD_DIR = @systemddir@
LAUNCHD_DIR = @launchddir@

$(GF_DISTRIBUTION):
	@if [ ! -d $(SYSTEMD_DIR) ]; then \
		$(MKDIR_P) $(DESTDIR)$(INIT_DIR); \
		$(INSTALL_PROGRAM) glusterd-$(GF_DISTRIBUTION) $(DESTDIR)$(INIT_DIR)/glusterd; \
	fi

install-exec-local: $(GF_DISTRIBUTION)

install-data-local:
if GF_DARWIN_HOST_OS
	$(MKDIR_P) $(DESTDIR)$(LAUNCHD_DIR)
	$(INSTALL_PROGRAM) glusterd.plist $(DESTDIR)$(LAUNCHD_DIR)/org.gluster.glusterd.plist
endif
