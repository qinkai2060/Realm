# Realm
新的数据库 realm:
>选择他因为代码简洁 简单易上手 ,用过CoreData 都知道 本次我就介绍项目中一些简单的使用
Realm 支持类型:
  ``` c++
（1）Realm支持以下的属性（property）种类：BOOL, bool, int, NSInteger, long, float, double, CGFloat, NSString, NSDate 和 NSData。
（2）你可以使用 RLMArray<Object> 和 RLMObject 来模拟对一或对多的关系(Realm也支持RLMObject继承)
 ```
1.创建数据
 ![image](https://github.com/qinkai2060/Realm/blob/master/creat.jpg?raw=true)
2. 新建表
 以我项目中一张user表为例
 ![image](https://github.com/qinkai2060/Realm/blob/master/user.jpg?raw=true)
 以 RLMArray<WARDBString> photos为例 user表中有多个WARDBString 对象的数组 在Realm 直接声明是有错的 需要 RLM_ARRAY_TYPE(WARDBString)包一层
 相当于协议
 Realm 注释:
    ![image](https://github.com/qinkai2060/Realm/blob/master/RLMArray.jpg?raw=true)
  某个对象作为 另外一个对象的RLMArray类型的属性 必须在RLMArray所在对象当中RRLM_ARRAY_TYPE(类名)
### 3.主键
  Realm 声明主键:
   ``` c++
     + (NSString *)primaryKey {
         return @"accountId";
      }
   ```

  Realm主键不自增
4:Realm CRUD
  (1). 创建并全量更新:
      ![image](https://github.com/qinkai2060/Realm/blob/master/全量更新与创建.jpg?raw=true)
      ![image](https://github.com/qinkai2060/Realm/blob/master/exmpl.jpg?raw=true)
 (2).获取user:
      > ![image](https://github.com/qinkai2060/Realm/blob/master/get.jpg?raw=true)
  (3).查询:
       1-主键查询删除
          ![image](https://github.com/qinkai2060/Realm/blob/master/查询并删除.jpg?raw=true)  
       2-条件查询并排序
          ![image](https://github.com/qinkai2060/Realm/blob/master/查询并排序.jpg?raw=true)
 (4). 修改:修改用户的性别
          ![image](https://github.com/qinkai2060/Realm/blob/master/修改.jpg?raw=true)
          
 ### 参考
  ###### [Realm数据库 从入门到“放弃”](http://www.cocoachina.com/ios/20161103/17935.html)
  ###### [iOS中Realm数据库的基本用法](https://www.cnblogs.com/h-tao/p/7130416.html)
  ###### [深入理解 Realm 的多线程处理机制](https://academy.realm.io/cn/posts/threading-deep-dive)
      
    
  
