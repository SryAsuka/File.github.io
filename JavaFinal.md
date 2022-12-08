# 新建数据库

  以一个仓库为例
  
  仓库 
  
  管理员（管理员号(Uid)，账号(Uacc)，密码(Upwd)，姓名(Uname)，电话(Uphone)，等级(Upower)）
  
    Create table User (
      Uid int primary key,
      Uacc varchar(10),
      Upwd varchar(16),
      Uname varchar(20),
      Uphone varchar(11),
      Upower int
      );
  
  仓库 （仓库号(Wid)，仓库名(Wname)，仓库地址(Wadd)）
  
    Create table WH (
      Wid int primary key,
      Wname varchar(20),
      Wadd varchar(50)
    );
  
  货物（货物号(Gid)，货物名称(Gname)，货物类型(Gtype)，库存(Stocks)，供应商(Supplier)）
  
    Create table Goods (
      Gno int(3) primary key,
      Gname varchar(20),
      Gtype varchar(20),
      Stocks int,
      Supplier varchar(20),
      );
  
  入库
  
  
  
  出库
  
  

# 分配任务

添加/删减：

 - 需求1：添加某货物 
  
 - 需求2：删除某货物

查找：

  - 需求1：获取仓库内所有的货物
  
  - 需求2：按照货物名称查找对应的货物信息
  
修改：

  - 需求1：修改库存

  - 需求2：
  
  - 需求3：


  
  
  
