# 问题 #
编写一个 SQL 查询，满足条件：无论 person 是否有地址信息，都需要基于上述两表提供 person 的以下信息：

FirstName, LastName, City, State
# 代码 #
```C++
select FirstName,Lastname,City,State from Person left join Address on Person.PersonId=Address.PersonId;
```
# 总结 #
Person表左连接 Address表查询。