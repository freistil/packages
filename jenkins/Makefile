NAME=jenkins
VERSION=1.454
FVERSION=0

.PHONY: package
package: contents/jenkins.war
	fpm -s dir -t deb -n $(NAME) -v $(VERSION)-freistil$(FVERSION) --prefix /opt/jenkins -d "sun-java6-jre (> 0)" -C contents

contents/jenkins.war: contents
	wget http://ftp.osuosl.org/pub/hudson/war/$(VERSION)/jenkins.war -O contents/jenkins.war

contents:
	mkdir contents
