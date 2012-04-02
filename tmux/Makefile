deb: tmux
	fpm -s dir -t deb -n tmux -v 1.6 -C pseudoroot -p tmux-VERSION_ARCH.deb \
		-d "libc6 (>= 2.8)" \
		-d "libncurses5 (>= 5.6+20071006-3)" \
		-d "libevent-1.4-2 (> 0)"

tmux-1.6.tar.gz:
	wget http://downloads.sourceforge.net/tmux/tmux-1.6.tar.gz

tmux-1.6: tmux-1.6.tar.gz
	tar xvf tmux-1.6.tar.gz

pseudoroot:
	cp -r auxfiles pseudoroot

tmux: tmux-1.6 pseudoroot
	cd tmux-1.6
	./configure --prefix=/usr
	make
	make install DESTDIR=../pseudoroot

.PHONY: deb tmux-1.6 pseudoroot tmux
