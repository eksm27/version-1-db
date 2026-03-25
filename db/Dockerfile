FROM mysql:8.0

# MySQL default config
ENV MYSQL_ROOT_PASSWORD=rootpass
ENV MYSQL_DATABASE=portfolio_db

# Create table + insert 1000 records
RUN echo "CREATE TABLE users ( \
id INT AUTO_INCREMENT PRIMARY KEY, \
firstname VARCHAR(50), \
lastname VARCHAR(50), \
dob DATE, \
email VARCHAR(100), \
mobilenumber VARCHAR(20) \
);" > /docker-entrypoint-initdb.d/init.sql

# Generate 1000 records
RUN for i in $(seq 1 1000); do \
echo "INSERT INTO users (firstname, lastname, dob, email, mobilenumber) VALUES ('user$i','test$i','1990-01-01','user$i@mail.com','90000000$i');" \
>> /docker-entrypoint-initdb.d/init.sql ; \
done