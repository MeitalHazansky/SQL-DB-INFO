# SQL-DB-INFO
Information about project SQL DB and configurations

# SQL Info
```
Database Name: coupons
```
```
Port: 3306
```
```
User Name: root
```
```
Password: 1234
```
```
Coupons-REST-Port: 8080
```
```
Angular Port: 4200
```
```
Spring Micro Service: 8888
```
```
CREATE TABLE coupons.`company` (
  `id` bigint(9) NOT NULL,
  `comp_name` varchar(45) NOT NULL,
  `password` varchar(45) NOT NULL,
  `email` varchar(45) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `comp_name_UNIQUE` (`comp_name`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='Company table.';

CREATE TABLE coupons.`company_coupon` (
  `comp_id` bigint(9) NOT NULL,
  `coupon_id` bigint(9) NOT NULL,
  PRIMARY KEY (`comp_id`,`coupon_id`),
  UNIQUE KEY `coupon_id_UNIQUE` (`coupon_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='Join table between companies and coupons.';

CREATE TABLE coupons.`coupon` (
  `id` bigint(9) NOT NULL,
  `title` varchar(45) NOT NULL,
  `start_date` date NOT NULL,
  `end_date` date NOT NULL,
  `amount` int(11) NOT NULL,
  `type` varchar(45) NOT NULL,
  `message` varchar(45) DEFAULT NULL,
  `price` decimal(20,4) NOT NULL,
  `image` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `title_UNIQUE` (`title`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='Coupons table.';

CREATE TABLE coupons.`customer` (
  `id` bigint(9) NOT NULL,
  `cust_name` varchar(45) NOT NULL,
  `password` varchar(45) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `cust_name_UNIQUE` (`cust_name`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='Customers table.';

CREATE TABLE coupons.`customer_coupon` (
  `cust_id` bigint(9) NOT NULL,
  `coupon_id` bigint(9) NOT NULL,
  PRIMARY KEY (`cust_id`,`coupon_id`),
  KEY `coupon_id_idx` (`coupon_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='Join between customers and coupons.';



```
