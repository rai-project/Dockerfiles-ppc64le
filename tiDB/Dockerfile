FROM ppc64le/golang:1.8.1
MAINTAINER "Yugandha Deshpande <yugandha@us.ibm.com>" 
RUN apt-get update \ 
 && apt-get install git make -y \
 && export GOPATH=/root/go \
 && mkdir -p /root/go/src/github.com/pingcap \
 && cd /root/go/src/github.com/pingcap \
 && git clone https://github.com/pingcap/tidb.git \
 && mkdir /logs \
 && touch /logs/unit-test \
 && cd tidb \
 && make default \
 && apt-get remove git make -y \
 && apt-get autoremove -y \ 
  && cp bin/goyacc /bin && cp bin/tidb-server /bin 
EXPOSE 4000
ENTRYPOINT ["tidb-server"]
CMD ["bash"]

 


