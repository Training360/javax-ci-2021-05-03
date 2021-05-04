# CI/CD implementálása Maven/Gradle, Jenkins és Docker eszközökkel tanfolyam

https://groovy-lang.org/style-guide.html

```shell
gradlew build
```

A `build/libs` kvt-ban létrejön egy `employees-0.0.1-SNAPSHOT.jar`

Ezt lehet futtatni:

```shell
java -jar employees-0.0.1-SNAPSHOT.jar
```

Kipróbálható a http://localhost:8080/swagger-ui.html címen.

```shell
docker run -d -e MYSQL_DATABASE=employees -e MYSQL_USER=employees -e MYSQL_PASSWORD=employees   -e MYSQL_ALLOW_EMPTY_PASSWORD=yes -p 3306:3306 --name employees-mariadb mariadb
```

```shell
docker exec -it employees-mariadb mysql employees
```

```sql
create table employees (id bigint not null auto_increment, emp_name varchar(255), primary key (id));
insert into employees(emp_name) values ("John Doe");
select * from employees;
drop table employees;
```