nobase_dist_eventdevent_DATA = \
	%D%/transfer/transfer.event \
	%D%/presence/presence.event \
	%D%/im/im.event \
	%D%/chat/chat.event \
	$(null)

nobase_eventdevent_DATA = \
	%D%/transfer/transfer.action \
	%D%/transfer/transfer-complete.action \
	%D%/transfer/transfer-error.action \
	%D%/presence/presence-away.action \
	%D%/presence/presence-away-message.action \
	%D%/presence/presence-back.action \
	%D%/presence/presence-back-message.action \
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

@EVENTD_EVENT_RULE@
@EVENTD_ACTION_RULE@

-include local-rules.mk
