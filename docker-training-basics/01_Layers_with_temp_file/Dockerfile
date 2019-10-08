FROM centos:latest
RUN sed -i -e "s,^mirrorlist,#mirrorlist," -e "s,^#baseurl,baseurl,"  /etc/yum.repos.d/CentOS-Base.repo
RUN yum install -y dialog dos2unix
WORKDIR /tmp
RUN dd if=/dev/zero of=downloaded_installation_package.bin bs=1M count=50
RUN echo do something
RUN rm downloaded_installation_package.bin
COPY run.sh /usr/local/bin/
RUN dos2unix /usr/local/bin/run.sh
ENTRYPOINT [ "/usr/local/bin/run.sh" ]
