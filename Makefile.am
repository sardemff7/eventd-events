nobase_dist_eventdevent_DATA = \
	%D%/transfer/transfer.event \
	%D%/presence/presence.event \
	%D%/im/im.event \
	%D%/chat/chat.event \
	$(null)

nobase_eventdevent_DATA = \
	%D%/transfer/transfer-complete.action \
	%D%/transfer/transfer-error.action \
	%D%/presence/presence-away.action \
	%D%/presence/presence-back.action \
	%D%/presence/presence-idle-back.action \
	%D%/presence/presence-idle.action \
	%D%/presence/presence-signed-off.action \
	%D%/presence/presence-signed-on.action \
	%D%/presence/presence.action \
	%D%/im/im.action \
	%D%/chat/chat.action \
	$(null)

EXTRA_DIST = \
	autogen.sh \
	README.md \
	$(nobase_eventdevent_DATA:.action=.action.in)
	$(null)

CLEANFILES = \
	$(nobase_eventdevent_DATA) \
	$(null)

SUBDIRS = po

%.event: %.event.in $(INTLTOOL_MERGE) $(wildcard $(top_srcdir)/po/*.po)
	$(INTLTOOL_V_MERGE) $(MKDIR_P) $(dir $@) && LC_ALL=C $(INTLTOOL_MERGE) $(INTLTOOL_V_MERGE_OPTIONS) -d -u -c $(top_builddir)/po/.intltool-merge-cache $(top_srcdir)/po $< $@

%.action: %.action.in $(INTLTOOL_MERGE) $(wildcard $(top_srcdir)/po/*.po)
	$(INTLTOOL_V_MERGE) $(MKDIR_P) $(dir $@) && LC_ALL=C $(INTLTOOL_MERGE) $(INTLTOOL_V_MERGE_OPTIONS) -d -u -c $(top_builddir)/po/.intltool-merge-cache $(top_srcdir)/po $< $@

-include local-rules.mk
