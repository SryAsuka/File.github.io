# 仓库管理系统

## 新建数据库
  
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
  
  货物（货物号(Gid)，货物名称(Gname)，货物类型(Gtype)）
  
    Create table Goods (
      Gno int(3) primary key,
      Gname varchar(20),
      Gtype varchar(20),
      Stocks int,
      Supplier varchar(20),
      );
  
  库存（编号(),货物名(),仓库名(),库存量(),）
  
  入库（入库号(Iid),货物名(Gname),仓库名(Wname),入库量(Istocks),管理员号(Uid),入库时间(IDate)）
  
    Create
  
  出库（出库号(Oid),货物名(Gname),仓库号(Wname),出库量(Ostocks),管理员编号(Uid),出库时间(ODate)）
  
  

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


  
  
  
