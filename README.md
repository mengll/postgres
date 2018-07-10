# postgres
postgresql
```
添加增序列
CREATE SEQUENCE gp_game_tags_id_seq
START WITH 3   //开始自增
INCREMENT BY 1  //增长步长
NO MINVALUE  
NO MAXVALUE  
CACHE 1;  
  
alter table gp_game_tags alter column id set default nextval('gp_game_tags_id_seq');

openrestry 中的pgsql pglib 的安装
yum install postgresql-devel


Update the RPM package
  rpm -ivh https://yum.postgresql.org/9.6/redhat/rhel-7.3-x86_64/pgdg-centos96-9.6-3.noarch.rpm
    
Update packages
  yum update
Install Postgres
   yum install postgresql96 postgresql96-server postgresql96-libs postgresql96-contrib postgresql96-devel
Initialize the DB

/usr/pgsql-9.6/bin/postgresql96-setup initdb
Start the Postgres service
  systemctl enable postgresql-9.6.service
  systemctl start postgresql-9.6.service 
```
