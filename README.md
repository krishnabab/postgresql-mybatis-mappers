# postgresql-mybatis-mappers

How to read json path value from json data
https://hashrocket.com/blog/posts/dealing-with-nested-json-objects-in-postgresql

Example postgresql queries

select empid from schema1.table1

select empid from schema1.table1 where data::json is not null

select empid from schema1.table1 where (data::json ->> 'empid') = '1'; 

select data::json ->> 'personalDetails'  from schema1.table1

select data::json #> array['personalDetails','firstName']  from schema1.table1

select  empid  from schema1.table1 where (data::json #>> array['personalDetails','firstName']) = 'krishna'
