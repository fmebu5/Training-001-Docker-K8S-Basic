FROM alpine:latest AS layer1

COPY test1.txt /tmp/a/
RUN dd if=/dev/zero of=/tmp/a/downloaded_installation_package.bin bs=1M count=50
RUN echo do something
RUN rm /tmp/a/downloaded_installation_package.bin


FROM alpine:latest
COPY --from=layer1 /tmp/a /tmp/b
RUN echo do something
RUN touch /tmp/b/test2.txt

VOLUME /tmp/c

CMD [ "/bin/sh", "-c", "ls -lr /tmp/*" ]
