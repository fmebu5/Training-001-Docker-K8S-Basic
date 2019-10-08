FROM alpine:latest
RUN apk add --no-cache dialog
WORKDIR /tmp
RUN dd if=/dev/zero of=downloaded_installation_package.bin bs=1M count=50 && \
	echo do something && \
	rm downloaded_installation_package.bin
COPY run.sh /usr/local/bin/
RUN cp /usr/local/bin/run.sh . && \
	sed 's/\r$//' run.sh > /usr/local/bin/run.sh
ENTRYPOINT [ "/usr/local/bin/run.sh" ]
