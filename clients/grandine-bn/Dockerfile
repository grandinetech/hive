ARG tag=unstable
ARG baseimage=sifrai/grandine

FROM $baseimage:$tag

RUN apt-get update && apt-get -y upgrade && apt-get install -y --no-install-recommends \
  xxd \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

ADD grandine.sh /grandine.sh
RUN chmod +x /grandine.sh
RUN grandine --version > /version.txt

ENTRYPOINT ["/grandine.sh"]
