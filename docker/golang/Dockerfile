From golang:1.11

COPY root /
RUN apt-get update || exit 0
RUN apt-get upgrade -y
RUN apt-get install -y ca-certificates dpkg gcc git musl-dev bash
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" \
    && chmod -R 777 "$GOPATH" \
    && chmod +x /entrypoint.sh
RUN go get github.com/tockins/realize
RUN go get -u github.com/gin-gonic/gin
WORKDIR $GOPATH
ENTRYPOINT ["/entrypoint.sh"]
CMD ["realize", "start"]
