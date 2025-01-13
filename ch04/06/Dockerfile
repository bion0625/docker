FROM diamol/golang AS builder

COPY main.go .
RUN go build -o /server

#app
FROM diamol/base

WORKDIR web
COPY --from=builder /server /web/server
COPY index.html .
RUN chmod +x /web/server

CMD ["/web/server"]
ENV USER=sixeyed
EXPOSE 80



#FROM diamol/golang
#
#WORKDIR web
#COPY index.html .
#COPY main.go .
#
#RUN go build -o /web/server
#RUN chmod +x /web/server
#
#CMD ["/web/server"]
#ENV USER=sixeyed
#EXPOSE 80