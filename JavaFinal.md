# 仓库管理系统

## 新建数据库
  ### 创建数据库 Warehouse
  
    Create database Warehose;
  
  ### 创建表
  管理员（管理员号(Uid)，账号(Uacc)，密码(Upwd)，姓名(Uname)，电话(Uphone)，等级(Upower)）
  
    Create table if not exists user (
      uid char(4),
      uacc varchar(10),
      upwd varchar(16),
      uname varchar(20)  primary key,
      uphone varchar(11),
      upower int
    );
    
    insert into user values ("U001","admin","123456","张三","12345678901",1);
  
  仓库 （仓库号(Wid)，仓库名(Wname)，仓库地址(Wadd)）
  
    Create table if not exists wh (
      wid char(4),
      wname varchar(20) primary key,
      wadd varchar(50)
    );
    
    insert into wh values ("W001","A","重庆");
  
  货物（货物号(Gid)，货物名(Gname)，货物类型(Gtype)）
  
    Create table if not exists goods (
      gid char(4),
      gname varchar(20) primary key,
      gtype varchar(20)
      );


    insert into goods values ("G001","苹果","水果");
    
  
  库存（编号(Sid),货物名(Gname),仓库名(Wname),库存量(SStocks)）
  
    Create table if not exists stocks (
      sid char(4) primary key,
      gname varchar(20),
      wname varchar(20),
      sstocks int,
      foreign key(gname) references goods(gname),
      foreign key(wname) references wh(wname)
    );
  
    insert into stocks values ("S001","苹果","A",500);
  
  入库（入库号(Iid),货物名(Gname),仓库名(Wname),入库量(Istocks),管理员名(Uname),入库时间(IDate)）
  
    Create table if not exists istocks (
      iid char(4) primary key,
      gname varchar(20),
      wname varchar(20),
      istocks int,
      uname varchar(20),
      idate date,
      foreign key(gname) references goods(gname),
      foreign key(wname) references wh(wname),
      foreign key(uname) references user(uname)
    );
    
    insert into istocks values ("I001","苹果","A",500,"张三",now());
  
  出库（出库号(Oid),货物名(Gname),仓库号(Wname),出库量(Ostocks),管理员编号(Uid),出库时间(ODate)）
  
    Create table if not exists istocks (
      oid char(7) primary key,
      gname varchar(20),
      wname varchar(20),
      ostocks int,
      uname varchar(20),
      odate date,
      foreign key(gid) references goods(gid),
      foreign key(wid) references wh(wid),
      foreign key(uid) references user(uid)
    );

    insert into istocks values ("Out001","苹果","A",100,"张三",now());

## 分配任务

 ### 管理员表
 
  - 登录账号，然后返回管理员等级，最高管理员（1），普通仓管（2） （形参账号密码，返回值int）
  - 返回全部管理员表信息 (无形参，返回值arraylist)
    
  >PS:(换回值为arraylist,下面是例子)
    
 ```ruby
     public ArrayList<String> selectData(){
        ArrayList<String> arrayList = new ArrayList<>();
        Connection connection = null;
        PreparedStatement preparedStatement = null;
        ResultSet resultSet = null;
        try {
            student student = new student();
            connection = useSql.getConnection();
            String sql = "SELECT * FROM `studens`";
            preparedStatement = connection.prepareStatement(sql);
            resultSet = preparedStatement.executeQuery();
            while(resultSet.next()){
                student.setName(resultSet.getString("name"));
                student.setAge(resultSet.getString("age"));
                student.setProvince(resultSet.getString("province"));
                student.setPhoneNum(resultSet.getString("phoneNum"));
                arrayList.add(student.getName());
                arrayList.add(student.getAge());
                arrayList.add(student.getProvince());
                arrayList.add(student.getPhoneNum());
            }
        } catch (SQLException throwables) {
            throwables.printStackTrace();
        }finally {
            useSql.release(connection,preparedStatement,resultSet);
        }
        return  arrayList;
    }
```
  - 修改管理员信息,根据姓名修改（无法修改管理员等级）  (形参 （旧名 + 新名 + ...） 除等级以外的，无返回值)
  - 根据 管理员id 查找管理员信息（形参（姓名） 返回值arraylist）
  - 增加管理员（全部形参，无返回值）
  - 删除管理员信息,根据姓名删除 （若等级为1，无法删除）（形参 （姓名） ，无返回值）

>之后的要求差不多都是这样

  ### 仓库表
  
  - 增加仓库
  - 查看全部仓库
  - 根据仓库名删除仓库
  - 根据仓库名查找仓库


  
  
  
