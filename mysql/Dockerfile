FROM mysql:8.0
#not a human, only for system  # this is to run the docker with non root user
RUN adduser -r expense
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=Expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions
#this is change the ownership to access the files with expense user
RUN chown -R expense:expense /var/lib/mysql /var/run/mysqld /var/sbin/mysqld
COPY scripts/*.sql /docker-entrypoint-initdb.d/
#at final we need to give the user
USER expense