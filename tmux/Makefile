NAME=tmux
VERSION=1.6

tmux-$(VERSION)_amd64.deb: tmux
	fpm -s dir -t deb -n tmux -v $(VERSION) -C pseudoroot -p tmux-VERSION_ARCH.deb \
		-d "libc6 (>= 2.8)" \
		-d "libncurses5 (>= 5.6+20071006-3)" \
		-d "libevent-1.4-2 (> 0)"

tmux-$(VERSION).tar.gz:
	wget http://downloads.sourceforge.net/tmux/tmux-$(VERSION).tar.gz

tmux-$(VERSION): tmux-$(VERSION).tar.gz
	tar xvf tmux-$(VERSION).tar.gz

pseudoroot:
	cp -r auxfiles pseudoroot

tmux: tmux-$(VERSION) pseudoroot
	cd tmux-$(VERSION) ;\
	./configure --prefix=/usr
	make -C tmux-$(VERSION)
	make -C tmux-$(VERSION) install DESTDIR=../pseudoroot

clean:
	rm -rf tmux-$(VERSION) pseudoroot/ tmux-$(VERSION).tar.gz tmux-$(VERSION)_amd64.deb

.PHONY: deb clean tmux
