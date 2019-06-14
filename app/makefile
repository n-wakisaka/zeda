include ../config

BINDIR=$(PREFIX)/bin

INSTALL=install -m 755

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
install: $(CONFIGGEN) $(CHKDEP) $(TARGET)
	@echo " INSTALL	" $^
	@$(INSTALL) $^ $(BINDIR)
clean:
	@echo " CLEAN"
	-@rm -f *.o *~ core $(TARGET)
uninstall: $(CONFIGGEN) $(CHKDEP) $(TARGET)
	@echo " UNINSTALL $^"
	-@rm -f $(addprefix $(BINDIR)/, $^)
