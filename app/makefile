include ../config

BINDIR=$(PREFIX)/bin

INSTALL=install -m 755
UNINSTALL=rm -f

LINK=-lzeda -lm

CONFIG=zeda-config
CONFIGGEN=zeda-config-gen
CHKDEP=zeda-chkdep
TARGET=$(CONFIG)

#####################################################################
all: $(TARGET)

$(CONFIG):
	@echo " GENERATE" $(CONFIG)
	-@rm -f $(CONFIG)
	@sh $(CONFIGGEN) -I $(PREFIX)/include -L $(PREFIX)/lib -l "$(LINK)" -v $(VERSION) > $(CONFIG)
install: $(INSTALLTARGET)
	@echo " INSTALL	" $^
	@$(INSTALL) $^ $(BINDIR)
clean:
	@echo " CLEAN"
	-@rm -f *.o *~ core $(TARGET)
uninstall:
	@echo " UNINSTALL	" $(CONFIGGEN)
	@$(UNINSTALL) $(BINDIR)/$(CONFIGGEN)
	@echo " UNINSTALL	" $(CHKDEP)
	@$(UNINSTALL) $(BINDIR)/$(CHKDEP)
	@echo " UNINSTALL	" $(TARGET)
	@$(UNINSTALL) $(BINDIR)/$(TARGET)
