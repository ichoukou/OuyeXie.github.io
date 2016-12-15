# Code

<pre>
<code>
Code highlighting produced by Actipro CodeHighlighter (freeware)http://www.CodeHighlighter.com/--> 1 table1结构如下
id    int
name  varchar(50)

declare @id int
declare @name varchar(50)
declare cursor1 cursor for         --定义游标cursor1
select * from table1               --使用游标的对象(跟据需要填入select文)
open cursor1                       --打开游标

fetch next from cursor1 into @id,@name  --将游标向下移1行，获取的数据放入之前定义的变量@id,@name中

while @@fetch_status=0           --判断是否成功获取数据
begin
update table1 set name=name+'1'
where id=@id                           --进行相应处理(跟据需要填入SQL文)

fetch next from cursor1 into @id,@name  --将游标向下移1行
end

close cursor1                   --关闭游标
deallocate cursor1
</code>
</pre>

# Reference

 - [general cursor](http://www.cnblogs.com/Gavinzhao/archive/2010/07/14/1777644.html)
 - [postgresql cursor](http://blog.csdn.net/xianyiqi/article/details/3960053)
 - [java jdbc postgresql cursor](http://blog.itpub.net/133735/viewspace-733295/)