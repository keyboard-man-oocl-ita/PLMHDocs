## 数据库表结构

#### 1、用户表（User）

```
user_id  varchar(255)  primary key,			
phone_number varchar(16)  not null,
password  varchar(255),
name  varchar(255),
car_license varchar(128) not noll
```



#### 2、员工表（Clerk）

```
clerk_id  varchar(255)  primary key,
phone_number  varchar(16)  not null,
password  varchar(255),
name  varchar(255) not null,
email  varchar(255),
role  int  not null,
status  int  not null,
managed_by  varchar(255)
```



#### 3、停车场表（Parking_Lot）

```
parking_lot_id  varchar(255)  primary key,
name  varchar(255),
description  varchar(255),
capacity  int  not null,
latitude  float,
longtitude  float,
created_by  varchar(255)  not null,
managed_by  varchar(255)
```



#### 4、订单表（Order）

```
order_id  varchar(255)  primary key,
clerk_id  varchar(255),
parking_lot_id  varchar(255),
user_id  varchar(255)  not null,
car_license  varchar(128)  not null,
created_time  long  not null,
end_time  long,
strategy_id  varchar(255),
status  int  not null
```

