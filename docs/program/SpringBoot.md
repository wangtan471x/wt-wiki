### springboot中@update使用

@update使用的两种情况
1.第一种情况
update操作传递一个参数

@Update(“update user set sex = “男” where id=#{id}”)
public int update(int id);

这种情况只有一个参数，参数id可以不用使用@param

2.第二种情况
update操作传递两个及以上参数

@Update(“update user set name =#{name} where id=#{id}”)
public int update(@Param(“id”) int id,@Param(“name”) String name);

这种情况有两个参数，需要使用@Param进行对两个参数进行区分，否则，在操作数据表时会报sql语句有注入风险。