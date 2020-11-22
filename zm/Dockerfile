FROM koenkk/rpi-zoneminder
RUN gpg --keyserver pgp.mit.edu --recv-keys \
        7638D0442B90D010 04EE7237B7D453EC && \
    gpg --armor --export 7638D0442B90D010 | apt-key add - && \
    gpg --armor --export 04EE7237B7D453EC | apt-key add -
RUN rm -rf /var/lib/apt/lists/* && apt-get update && apt-get install -y php7.0-apcu  unzip
RUN mkdir -p /usr/share/zoneminder/www/api/app/Plugin
ADD c3976f1478c681b0bbc132ec3a3e82c3984eeed5.zip /tmp/
WORKDIR /usr/share/zoneminder/www/api/app/Plugin
RUN unzip /tmp/c3976f1478c681b0bbc132ec3a3e82c3984eeed5.zip
RUN mv crud-c3976f1478c681b0bbc132ec3a3e82c3984eeed5 Crud
