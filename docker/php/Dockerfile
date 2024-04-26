FROM centos:centos7

# PHPとApacheのインストール
RUN yum install -y epel-release && \
    yum install -y php php-mysql php-cli httpd && \
    yum clean all && \
    systemctl enable httpd.service

# カスタムのApache設定ファイルをコピーする
COPY apache2.conf /etc/httpd/conf.d/

# ポート80を公開
EXPOSE 80

# Apacheを実行
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
