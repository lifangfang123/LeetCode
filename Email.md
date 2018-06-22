# 问题 #
编写一个 SQL 查询，查找 Person 表中所有重复的电子邮箱。
# 代码 #
```C++
select Email
from Person
group by Email having count(Email)>1
```

# 总结 #
从person表中选出出现次数大于1的电子邮箱。