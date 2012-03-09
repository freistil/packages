NAME=jenkins
VERSION=1.454
FVERSION=0


.PHONY: package pkgfiles

package: pkgfiles
	fpm -s dir -t deb -n $(NAME) -v $(VERSION)-freistil$(FVERSION) --prefix /opt/jenkins -d "sun-java6-jre (> 0)" -C _contents

pkgfiles: _contents/jenkins.war

_contents/jenkins.war: _contents
	wget http://ftp.osuosl.org/pub/hudson/war/$(VERSION)/jenkins.war -O _contents/jenkins.war

_contents: 
	mkdir _contents
