FROM mysql:8.0

ENV MYSQL_DATABASE=laravel_local \
    MYSQL_USER=phper \
    MYSQL_PASSWORD=secret \
    MYSQL_ROOT_PASSWORD=secret \
    TZ=Asia/Tokyo

COPY ./my.cnf /etc/mysql/conf.d/my.cnf
RUN chmod 644 /etc/mysql/conf.d/my.cnf

# Windows環境でボリュームマウントを行うと、ファイルパーミッションが777となるようです。
# my.cnf に書き込み権限が付いてるとMySQLの起動時にエラーが発生します。
# その対策としてボリュームマウントではなくDockerfileを作成して my.cnf ファイルコピー、
# 読み取り専用に権限変更してます。