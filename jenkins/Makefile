NAME=jenkins
VERSION=1.454
FVERSION=0

PKGDIR=_contents

.PHONY: package pkgfiles

package: pkgfiles
	fpm -s dir -t deb -n $(NAME) -v $(VERSION)-freistil$(FVERSION) --prefix /opt/jenkins -d "sun-java6-jre (> 0)" -C $(PKGDIR)

pkgfiles: $(PKGDIR)/jenkins.war

$(PKGDIR)/jenkins.war: $(PKGDIR)
	wget http://ftp.osuosl.org/pub/hudson/war/$(VERSION)/jenkins.war -O $(PKGDIR)/jenkins.war

$(PKGDIR): 
	mkdir $(PKGDIR)
