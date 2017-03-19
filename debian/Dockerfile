FROM intimatemerger/mecab-python:0.996

LABEL maintainer "mats116 <mats.kazuki@gmail.com>"

COPY mecabrc /etc/mecabrc

RUN apt-get update && \
    apt-get install -y git make curl xz-utils file sudo && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    git clone --depth 1 https://github.com/neologd/mecab-ipadic-neologd.git /tmp/neologd && \
    /tmp/neologd/bin/install-mecab-ipadic-neologd -n -y && \
    rm -rf /tmp/neologd

CMD ["/usr/bin/mecab"]
