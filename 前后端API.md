# 前后端API接口

## Base url

- prod:

  ```待定```

- dev:

  ```待定```



## GET请求通用Headers

```
headers: {
	Authorization: [token]
}
```



## Users API

```
/users		【POST】
REQUEST
data: {
	name: string,
	password: string,
	phoneNumber: string,
	carLicense: string
}

RESPONSE
data: {
	name: string,
	phoneNumber: string,
	carLicense: string
}


/users/{id}		【PUT】
REQUEST
data: {
	name: string,
	password: string,
	phoneNumber:string,
	carLicense: string
}

RESPONSE
data: {
	name: string,
	phoneNumber:string,
	carLicense: string
}


```



## Clerks API

```
/clerks 【POST】
REQUEST
data: {
	phoneNumber: string,
	email: String,
	name: String,
	role: int
}
RESPONSE
data: {
	不要带密码
}
```

```
/clerks 【PUT】
REQUEST
data: {
	phoneNumber: string,
	email: String,
	name: String,
	role: int
}
RESPONSE
data: {
	不要带密码
}
```

```
/clerks 【GET】
REQUEST
params: {
	page: int,
	pageSize: int
}
```

```
/clerks 【GET】
REQUEST
params: {
	managedBy: String
}
RESPONSE
List<Clerk>
```

```
/clerks/{id} 【GET】
RESPONSE
List<Clerk>
```



## Orders API

```java
/orders 【POST】
REQUEST
data: {
	carLicense: String,
	createTime: Long,
	userId: String
}
RESPONSE
data: {
	carLicense: String,
	createTime: Long,
	UserId: String
	orderId: String
	status: String  // 默认为0，抢单中
}
```

```
/orders 【GET】
REQUEST
params: {
	page: int,
	pageSize:int
}
RESPONSE
data: {
	List<Order>对象
}

```

```
/oders/{id} 【PUT】
REQUEST
data: {
	clerkId: String/null,
	parkingLotId: String/null,
	status: int,
	endTime: long/null
}
RESPONSE
data: {
JSON order全部
}

```

## ParkingLots API

```
/parkingLots 【POST】
REQUEST
data: {
	description: null/String,
	name: String,
	capacity: int,
	latitude: float/null,
	longitude: float/null,
	createdBy: String
}
RESPONSE
data: JSON创建好的

```

```
/parkingLots 【PUT】
REQUEST
data: {
	除 parkingLotId和createdBy外均可
}
RESPONSE
data: {
	JSON: 改新后的
}

```

```
/parkingLots 【GET】
params: {
	page: int,
	pageSize: int,
}
RESPONSE
data: {
	JSON: List<ParkingLot>
}

```

```
/parkingLots 【GET】
params: {
	createdBy: String
}
RESPONSE
data: {
	JSON: List<ParkingLot>
}

```

```
/parkingLots/{id} 【GET】
同上

```



# 注意

1. RESPONSE不要带密码！！！
2. 默认值：
   1. Clerk：
      1. password自动生成
      2. status：默认active
   2. Order：
      1. status：默认抢单中
3. headers带token
4. status发出去是int，回来是String（后台处理）
