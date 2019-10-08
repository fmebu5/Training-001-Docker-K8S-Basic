FROM alpine:latest
RUN apk add --no-cache dialog
WORKDIR /tmp

ENV VERSION 1.2.3
ARG PARAM1
ARG PARAM2
ARG SECRET
ENV TARGETDIR=/opt/software/$VERSION
RUN echo "$VERSION -- $TARGETDIR"

RUN mkdir -p /opt/software/$VERSION

RUN touch $TARGETDIR/any_installation_steps

RUN echo "$SECRET: do something with secret" 

RUN echo "do more things with '$PARAM1' and '$PARAM2'" 

COPY run.sh /usr/local/bin/
RUN cp /usr/local/bin/run.sh . && \
	sed 's/\r$//' run.sh > /usr/local/bin/run.sh
ENTRYPOINT [ "/usr/local/bin/run.sh" ]
