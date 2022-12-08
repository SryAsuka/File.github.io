# 仓库管理系统

## 新建数据库
  ### 创建数据库 Warehouse
  
    Create database Warehose;
  
  ### 创建表
  管理员（管理员号(Uid)，账号(Uacc)，密码(Upwd)，姓名(Uname)，电话(Uphone)，等级(Upower)）
  
    Create table if not exists user (
      uid int primary key,
      uacc varchar(10),
      upwd varchar(16),
      uname varchar(20),
      uphone varchar(11),
      upower int
    );
    
    insert into user values (001,"admin","123456","张三","12345678901",1);
  
  仓库 （仓库号(Wid)，仓库名(Wname)，仓库地址(Wadd)）
  
    Create table if not exists wh (
      wid int primary key,
      wname varchar(20),
      wadd varchar(50)
    );
    
    insert into wh values (10001,"A","重庆");
  
  货物（货物号(Gid)，货物名(Gname)，货物类型(Gtype)）
  
    Create table if not exists goods (
      gid int primary key,
      gname varchar(20),
      gtype varchar(20)
      );


    insert into goods values (10001,"苹果","水果");
    
  
  库存（编号(Sid),货物名(Gname),仓库名(Wname),库存量(SStocks)）
  
    Create table if not exists stocks (
      sid int primary key,
      gid int,
      gname varchar(20),
      wid int,
      wname varchar(20),
      sstocks int,
      foreign key(gid) references goods(gid),
      foreign key(wid) references wh(wid)
    );
  
    insert into stocks values (001,001,"苹果",001,"A",500);
  
  入库（入库号(Iid),货物名(Gname),仓库名(Wname),入库量(Istocks),管理员名(Uname),入库时间(IDate)）
  
    Create table if not exists istocks (
      iid int primary key,
      gid int,
      gname varchar(20),
      wid int,
      wname varchar(20),
      istocks int,
      uid int,
      uname varchar(20),
      idate date,
      foreign key(gid) references goods(gid),
      foreign key(wid) references wh(wid),
      foreign key(uid) references user(uid)
    );
    
    insert into istocks values (001,001,"苹果",001,"A",500,001,"张三",now());
  
  出库（出库号(Oid),货物名(Gname),仓库号(Wname),出库量(Ostocks),管理员编号(Uid),出库时间(ODate)）
  
    Create table if not exists ostocks (
      oid int primary key,
      gid int,
      gname varchar(20),
      wid int,
      wname varchar(20),
      ostocks int,
      uid int,
      uname varchar(20),
      odate date,
      foreign key(gid) references goods(gid),
      foreign key(wid) references wh(wid),
      foreign key(uid) references user(uid)
    );

    insert into ostocks values (001,001,"苹果",001,"A",100,001,"张三",now());

# 分配任务

 管理员表
 
 -通过等级区分



  
  
  
