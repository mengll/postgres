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

```
