MAINTAINERCLEANFILES=Makefile.in
bin_PROGRAMS=ircd
ircd_SOURCES= balloc.c          \
              channel.c         \
              channel_mode.c    \
              client.c          \
              csvlib.c          \
              dbuf.c            \
              dynlink.c         \
              event.c           \
              fdlist.c          \
              fileio.c          \
              getopt.c          \
              hash.c            \
              hook.c            \
              hostmask.c        \
              irc_getaddrinfo.c \
              irc_getnameinfo.c \
              irc_res.c         \
              irc_reslib.c      \
              irc_string.c      \
              ircd.c            \
              ircd_signal.c     \
              list.c            \
              listener.c        \
              m_error.c         \
              match.c           \
              memory.c          \
              modules.c         \
              motd.c            \
              packet.c          \
              parse.c           \
              s_conf.c          \
              s_bsd_epoll.c     \
              s_bsd_poll.c      \
              s_bsd_sigio.c     \
              s_bsd_devpoll.c   \
              s_bsd_kqueue.c    \
              s_bsd_select.c    \
              s_bsd_win32.c     \
              restart.c         \
              resv.c            \
              rsa.c             \
              s_auth.c          \
              s_bsd.c           \
              s_gline.c         \
              s_log.c           \
              s_misc.c          \
              s_serv.c          \
              s_user.c          \
              s_stats.c         \
              send.c            \
              sprintf_irc.c     \
              tools.c           \
              version.c         \
              whowas.c          \
              ircd_parser.y     \
              ircd_lexer.l      

if HAVE_CRYPT
ircd_SOURCES+=crypt.c
endif

ircd_LDFLAGS=-export-dynamic $(OPENSSL_LDFLAGS)
AM_CPPFLAGS=$(LTDLINCL) -I$(top_srcdir)/include -I$(top_srcdir)/lib/pcre $(OPENSSL_INCLUDES)

if USE_SHARED_MODULES
ircd_LDADD=$(LIBLTDL)
ircd_DEPENDENCIES=$(LTDLDEPS)
else
ircd_LDADD=$(top_builddir)/modules/libmodules.la
endif
ircd_LDADD+=$(top_builddir)/lib/pcre/libpcre.a $(OPENSSL_LIBS)
AM_YFLAGS=-d
