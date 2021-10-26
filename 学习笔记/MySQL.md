

# 第一章       数据库基础



## 数据库系统概述



### 数据库技术的发展

（1）人工管理阶段

（2）文件系统阶段

（3）数据库系统阶段



### 数据库系统的组成

数据库系统（Database System，DBS）是采用数据库技术的计算机系统，是由数据库（数据）、数据库管理系统、数据库管理员、支持数据库系统的硬件和软件（应用开发工具、应用系统等）以及用户5构成的运行实体，如图所示。数据管理员（Database Administrator，DBA）是对数据库进行规划、设计、维护和监视等的专业管理人员，在数据库系统中起着非常重要的作用。

![](C:\Users\FY\Desktop\Python笔记\学习笔记\MySQL_image\数据库系统的组成.gif)



## 数据模型



### 数据模型的概念

数据模型是数据库系统的核心与基础，是关于描述数据与数据之间的联系、数据的语义、数据一致性约束的概念性工具的集合。数据模型通常是由数据结构、数据操作和完整约束3部分组成的，分别如下。

（1）数据结构：是对系统静态特征的描述，描述对象包括数据的类型、内容、性质和数据之间的相互关系。

（2）数据操作：是对系统动态特征的描述，是对数据库各种对象实例的操作。

（3）完整性约束：是完整性规则的集合，它定义了给定数据模型中数据及其联系所具有的制约和一村规则。



### 常见的数据模型

常见的数据库数据模型主要有层次模型、网状模型和关系模型，下面分别进行介绍。

（1）层次模型：用树状结构表示实体类型及实体间联系的数据模型称为层次模型，如图所示。它具有一下特点。一、每棵树有且仅有一个无双亲节点，成为根。二、树中除根外所有节点有且仅有一个双亲。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\层次模型.jpg)

（2）网状模型：用有向图结构表示实体类型及实体间联系的数据模型称为网状模型，用网状模型编写应用程序极其复杂，数据的独立性较差。

（3）关系模型：以二维表来描述数据。关系模型中，，每个表有多个字段列和记录行，每个字段列有固定的属性（数字、字符、日期等）关系模型数据结构简单、清晰、具有很高的数据独立性，是目前主流的数据库数据模型。关系模型的基本属于如下。

关系：一个二维表就是一个关系。

元组：二维表中的一行，即表中的记录。

属性：二维表的一列，用类型和值表示。

域：每个属性去质的变化范围，如性别的域为{男，女}。

关系中的数据约束如下。

实体完整性约束：约束关系的主键中属性值不能为控空值。

参照完整性约束：关系之间的基本约束。

用户定义的完整性约束：反映了具体应用中数据的语义要求。



### 关系数据库的规范化

关系数据库的规范化理论为：关系数据库中的每个关系都要满足一定的规范。根据满足规范的条件不同，可以分为5个等级：第一范式、第二范式......第五范式。其中，NF 式 Normal Form 的缩写。一般情况下，只要把数据规范到第三范式标准就可以满足需要了。下面举例介绍前三种范式。

1、第一范式（1NF）：
所谓第一范式（1NF）是指在关系模型中，对于添加的一个规范要求，所有的域都应该是原子性的，即数据库表的每一列都是不可分割的原子数据项，而不能是集合，数组，记录等非原子数据项。即实体中的某个属性有多个值时，必须拆分为不同的属性。在符合第一范式（1NF）表中的每个域值只能是实体的一个属性或一个属性的一部分。简而言之，第一范式就是无重复的域。
说明：在任何一个关系数据库中，第一范式（1NF）是对关系模式的设计基本要求，一般设计中都必须满足第一范式（1NF）。不过有些关系模型中突破了1NF的限制，这种称为非1NF的关系模型。换句话说，是否必须满足1NF的最低要求，主要依赖于所使用的关系模型。

2、第二范式（2NF）
在1NF的基础上，非码属性必须完全依赖于候选码（在1NF基础上消除非主属性对主码的部分函数依赖）
第二范式（2NF）是在第一范式（1NF）的基础上建立起来的，即满足第二范式（2NF）必须先满足第一范式（1NF）。第二范式（2NF）要求数据库表中的每个实例或记录必须可以被唯一地区分。选取一个能区分每个实体的属性或属性组，作为实体的唯一标识。例如在员工表中的身份证号码即可实现每个一员工的区分，该身份证号码即为候选键，任何一个候选键都可以被选作主键。在找不到候选键时，可额外增加属性以实现区分，如果在员工关系中，没有对其身份证号进行存储，而姓名可能会在数据库运行的某个时间重复，无法区分出实体时，设计辟如ID等不重复的编号以实现区分，被添加的编号或ID选作主键。（该主键的添加是在ER设计时添加，不是建库时随意添加）
第二范式（2NF）要求实体的属性完全依赖于主关键字。所谓完全依赖是指不能存在仅依赖主关键字一部分的属性，如果存在，那么这个属性和主关键字的这一部分应该分离出来形成一个新的实体，新实体与原实体之间是一对多的关系。为实现区分通常需要为表加上一个列，以存储各个实例的唯一标识。简而言之，第二范式就是在第一范式的基础上属性完全依赖于主键。

3、第三范式（3NF）
在2NF基础上，任何非主属性不依赖于其它非主属性（在2NF基础上消除传递依赖）
第三范式（3NF）是第二范式（2NF）的一个子集，即满足第三范式（3NF）必须满足第二范式（2NF）。简而言之，第三范式（3NF）要求一个关系中不包含已在其它关系已包含的非主关键字信息。例如，存在一个部门信息表，其中每个部门有部门编号（dept_id）、部门名称、部门简介等信息。那么在员工信息表中列出部门编号后就不能再将部门名称、部门简介等与部门有关的信息再加入员工信息表中。如果不存在部门信息表，则根据第三范式（3NF）也应该构建它，否则就会有大量的数据冗余。简而言之，第三范式就是属性不依赖于其它非主属性，也就是在满足2NF的基础上，任何非主属性不得传递依赖于主属性。



### 关系数据库的设计原则

（1）数据库内数据文件的数据组织应获得最大限度的共享、最小的冗余度，消除数据及数据依赖关系中的冗余部分，使依赖于同一个数据模型的数据达到有效的分离。

（2）保证输入、修改数据是数据的一致性与正确性。

（3）保证数据与使用数据的应用程序之间的高度独立性。



### 实体与关系

实体之间有3种关系，分别如下：

（1）一对一关系：是指表 A 中的一条记录在表 B 中有且只有一条相匹配的记录。在一对一关系中，大部分相关信息都在一个表中。

（2）一对多关系：是指表 A 中的行可以在表 B 中有许多匹配行，但是表 B 中的行只能在表 A 中有一个匹配行。

（3）多对多关系：是指关系中每个表的行在相关表中具有多个匹配行。在数据库中，多对多关系的建立是依赖第三个表（称作连接表）实现的，连接表包括相关的两个表的主键列，然后从两个相关表的主键列分别创建于连接表中的匹配列的关系。



## 数据库的体系结构



### 数据库三级模式结构

数据库的三级模式结构是指模式。外模式和内模式。

（1）模式：模式也称逻辑模式或概念模式，是数据库中全体数据的逻辑模式和特征的描述，是所有用户的公共数据视图。一个数据库只有一个模式。模式处于三级结构的中间层。

（2）外模式：外模式也称用户模式，是数据库用户（包括应用程序员和最终用户）能够看见和使用的局部数据的逻辑结构和特征的描述，是数据库用户的数据视图，是与某一应用有关的数据的逻辑表示。外模式是模式的子集，一个数据库可以有多个外模式。

（3）内模式：内模式也称存储模式，是数据物理结构和存储方式的描述，是数据在数据库内部的表示方法。一个数据库只有一个内模式。



### 三级模式之间的映射

（1）外模式/模式映射：对于同一个模式有任意多个外模式。对于每一个外模式，数据库系统都有一个外模式/模式映射。当模式改变时，由数据库管理员对各个外模式/模式映射做相应的改变，可以是外模式保持不变。这样，依据数据外模式编写的应用程序就不用修改，保证了数据与程序的逻辑独立性。

（2）数据库中只有一个模式和内模式，所以模式/内模式映射是唯一的，它定义了数据库的全局逻辑结构与存储结构之间的对应关系。当数据库的存储结构改变时，由数据库管理员对模式/内模式映射做相应改变，可以使模式保持不变，应用程序相应地也不做变动。这样，保证了数据与程序的物理独立性。





# 第二章      初始 MySQL

# 第三章       使用 MySQL 图形化管理工具





# 第四章数据库操作



## 认识数据库



### 数据库基本概念

数据库（Database）是按照数据结构来组织、存储和管理数据的仓库，是存储在一起的相关数据的集合。其优点主要体现在以下几方面。

（1）减少数据的冗余度，节省数据的存储空间；

（2）具有较高的数据独立性和易扩充性；

（3）实现数据资源的充分共享。



### 数据库常用对象

在 MySQL 的数据库中，表、视图、存储过程和索引等具体存储数据或对数据进行操作的实体都被称为数据库对象。（1）表；（2）字段；（3）索引；（4）视图；（5）存储过程。



### 系统数据库

（1）information_schema 数据库；（2）performance_schema 数据库；（3）sakila 数据库；（4）test 数据库；（5）world 数据库。



## 创建数据库

在 MySQL 中，可以使用 CREATE DATABASE 语句和 CREATE SCHEMA 语句创建 MySQL 数据库，其语法如下。

```mysql
CREATE {DATABASE|SCHEMA} [IF NOT EXISTS] 数据库名
[
    [DEFAULT] CHARACTER SET[=] 字符集 |
    [DEFAULT] COLLATE [=] 校对规则名称
];
```

在语法中，花括号 ”{}“ 表示必选项；中括号 ”[]“ 表示可选项；竖线 ”|“ 表示分隔符两侧的内容为”或“的关系。在上面的语法中，{DAEABASE|SCHEMA}表示要么使用关键字 DADTABASE，要么使用 SCHEMA，但不能全不使用。

参数说明如下。

（1）[IF NOT EXISTS]：可选项，表示在创建数据库前进行判断，只有该数据库目前尚未存在时才执行创建语句。

（2）数据库名：必须指定的，在文件系统中，MySQL 的数据存储区将以目录方式表示 MySQL 数据库。因此，这里的数据库必须符合操作系统文件夹的命名规则，而在 MySQL 中是不区分大小写的。

（3）[DEFAULT]：可选项，表示指定默认值。

（4）CHARACTER SET [=] 字符集：可选项，用于指定数据库的字符集。如果不想指定数据库所使用的字符集，那么就可以不使用该项，这时 MySQL 会根据 MySQL 服务器默认使用的字符集来创建该数据库。这里的字符集可以是 GB2312 或者 GBK（简体中文）、UTF8（针对 Unicode 的可变长度的字符编码，也称万国码）、BIG5（繁体中文）、Latin1（拉丁文）等其中最常用的就是 UTF8 和 GBK。

（5）COLLATE [=] 校对规则名称：可选项，用于指定字符集的校对规则。例如，utf8_bin 或者 gbk_chinese_ci。具体都哪些校对规则，可以在 MySQL 的图形化工具 Workbench 的创建数据库的窗口中找到。



### 通过 CREATE DATABASE 语句创建基本数据库

通过 CREATE DATABASE 语句创建一个名称为 db_admin 的数据库，具体代码如下：

```mysql
create database db_admin;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CREATE_DATABASE.png)



### 通过 CREATE SCHEMA 语句创建基本数据库

实际上，还可以通过语法中给出的 CREATE DATABASE 来创建数据库，两者功能是一样的。通过 CREATE DATABASE 语句创建一个名称为 db_admin1 的数据库，具体代码如下：

````mysql
create schema db_admin1;
````

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CREATE_SCHEMA.png)



### 创建指定字符集的数据库

在创建数据库时，如果不指定其使用的字符集或者是字符集的校对规则，那么将根据 my.ini 文件中指定的 default-character-set 变量的值来设置其使用的字符集。从创建数据库的基本语法中可以看出，在创建数据库时，还可以指定数据库所使用的字符集，下面将通过一个具体的例子来演示如何在创建数据库时，指定字符集。通过 CREATE DATABASE 语句创建一个名称为 db_test 的数据库，并指定其字符集为 GBK，具体代码如下。

```mysql
CREATE DATABASE db_test
CHARACTER SET = GBK;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建指定字符集的数据库.png)



### 创建数据库前判断是否存在同名数据库

在 MySQL 中，不允许同一系统中存在两个相同名称的数据库，如果要创建的数据库名称已经存在，那么系统将给出以下错误信息。

```mysql
ERROR 1007(HY000):Can't create database 'db_test'; database exists
```

为了避免错误的发生，在创建数据库时，可以使用 IF NOT EXISTS 选项来实现在创建数据库前判断该数据库是否存在，只有不存在时才会进行创建。通过 CREATE DATABASE 语句创建一个名称为 db_test1 的数据库，并在创建前判断该数据库名称是否存在，只有不存在时才创建，具体代码如下。

```mysql
CREATE DATABASE IF NOT EXISTS db_test1;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建数据库前判断是否存在同名数据库.png)



## 查看数据库

成功创建数据库后，可以使用 SHOW 命令查看 MySQL 服务器中的所有数据库信息，语法如下。

```mysql
SHOW {DATABASES|SCHEMAS}
[LIKE '模式' WHERE 条件]
;
```

参数说明如下。

（1）{DATABASES|SCHEMAS}：表示必须有一个是必选项，用于列出当前用户权限范围内所能查看到的所有数据库名称。这两个选项的结果是一样的，使用哪个都可以。

（2）LIKE：可选项，用于指定匹配模式。

（3）WHERE：可选项，用于指定数据库名称查询范围的条件。

下面使用 SHOW DTABASES 语句查看 MySQL 服务器中的所有数据库名称，代码及运行结果如下。

```mysql
SHOW DATABASES;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查看数据库.png)



如果 MySQL 服务器中数据库比较多，也可以通过指定匹配模式来筛选想要得到的数据库，下面将通过一个具体的实例来演示如何通过 LIKE 关键字筛选要查看的数据库。筛选以 db_开头的数据库名称，代码如下。

```mysql
SHOW DATABASES LIKE 'db_%';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\筛选db开头的数据库名称.png)



## 选择数据库

选择名称为 db_admin 的数据库，设置其为当前默认的数据库，具体代码如下。

```mysql
USE db_admin;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\选择数据库.png)



## 修改数据库

在 MySQL 中，创建一个数据库后，还可以对其进行修改，不过这里的修改是指可以修改被创建数据库的相关参数，并不能修改数据库名。修改数据库名不能使用这个语句。修改数据库可以使用 ALTER DATABASE 或者 ALTER SCHEMA 语句来实现。修改数据库的语句的语法格式如下。

````mysql
ALTER {DATABASE|SCHEMA} [数据库名]
[DEFAULT] CHARACTER SET [=] 字符集
|[DEFAULT] COLLATE [=] 校对规则名称
````

参数说明如下。

（1）{DATABASE|SCHEMA}：表示必须有一个是必选项，这两个选项的结果是一样的，使用哪个都可以。

（2）[数据库名]：可选项，如果不指定要修改的数据库，那么将表示修改当前（默认）的数据库。

（3）[DEFAULT]：可选项，表示指定默认值。

（4）CHARACTER SET [=] 字符集：可选项，用于指定数据库的字符集。如果不想指定数据库所使用的字符集，那么就可以不使用该项，这时 MySQL 会根据 MySQL 服务器默认使用的字符集来创建该数据库。这里的字符集可以是 GB2312 或者 GBK（简体中文）、UTF8（针对 Unicode 的可变长度的字符编码，也称万国码）、BIG5（繁体中文）、Latin1（拉丁文）等其中最常用的就是 UTF8 和 GBK。

5）COLLATE [=] 校对规则名称：可选项，用于指定字符集的校对规则。例如，utf8_bin 或者 gbk_chinese_ci。具体都哪些校对规则，可以在 MySQL 的图形化工具 Workbench 的创建数据库的窗口中找到。

修改创建的数据库 db_admin，设置默认字符集和校对规则，具体代码如下。

```mysql
ALTER DATABASE db_admin
      DEFAULT CHARACTER SET GBK
      DEFAULT COLLATE gdk_chinese_ci;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\修改数据库.png)



## 删除数据库

在 MySQL 中，可以通过使用 DROP DATABASE 语句或者 DROP SCHEMA 语句来删除已经存在的数据库。使用该命令删除数据库的同时，该数据库中的表，以及表中的数据也将永久删除，因此在使用该语句删除数据库时一定要小心，以免误删除有用的数据库。DROP DATABASE 或者 DROP SCHEMA 语句的语法格式如下。

```mysql
DROP {DATABASE|SCHEMA} [IF EXISTS] 数据库名;
```

参数说明如下。

（1）{DATABASE|SCHEMA}：表示必须有一个是必选项，这两个选项的结果是一样的，使用哪个都可以。

（2）[IF EXISTS]：用于指定在删除数据前，先判断该数据库是否已经存在，只有已经存在时，才会执行删除操作，这样可以避免删除不存在的数据库时，产生异常。

通过 DROP DATABASE 语句删除名为 db_admin 的数据库，具体代码如下。

```mysql
DROP DATABASE db_admin;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\删除数据库.png)





# 第五章     存储引擎及数据类型



## MySQL 存储引擎

存储引擎其实就是如何存储数据、如何为存储的数据建立索引和如何更新、查询数据等技术的实现方法。因为在关系数据库中数据是以表的形式存储的，所以存储引擎也可以成为表类型（即存储和操作此表的类型）。在 Oracle 和 SQL server 等数据库中只有一种存储引擎，所有数据存储管理机制都是一样的；而 MySQL 数据库提供了多种存储引擎。用户可以根据不同需求为数据表选择不同的存储引擎，用户也可以根据需要编写自己的存储引擎。



### MySQL 存储引擎的概念

MySQL 中的数据用各种不同的技术存储在文件（或者内存）中。这些技术中美一种技术都使用不同的存储机制。索引技巧、锁定水平并且最终提供广泛的、不同的功能和能力。通过选择不同的技术，能够获得额外的速度或者功能，从而改善应用的整体功能。这些不同的技术以及配套的相关功能在 MySQL 中被称作存储引擎（也称作表类型）。MySQL 默认配置了许多不同的存储引擎，可以预先设置或者在 MySQL 服务器中启用。可以选择适用于服务器、数据库和表格的存储引擎，以便在选择如何存储信息。如何检索这些信息以及需要的数据结合什么性能和功能的时候为其提供最大的灵活性。



### 查询 MySQL 中支持的存储引擎

**（1）查询支持的全部存储引擎**

在 MySQL 中，可以使用 SHOW ENGINES 语句查询 MySQL 中支持的存储引擎。其查询语句如下。

```mysql
SHOW ENGINES;
```

SHOW ENGINES 语句可以用 “;” 结束，也可以用 “\g” 或者 “\G” 结束。“\g” 与 “;” 的作用是相同的，“\G” 可以让结果显示得更加美观。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查询存储引擎.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查询存储引擎G.png)



**（2）查询默认的存储引擎**

如果想要知道当前 MySQL 服务器采用的默认存储引擎是什么，可以通过执行 SHOW VARIABLES 命令来查看。查询默认存储引擎的 SQL 语句如下。

````mysql
SHOW VARIABLES LIKE '%storage_engine%';
````

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查询默认存储引擎.png)

可见当前 MySQL 服务器采用的默认存储引擎时 InnoDB。



### InnoDB 存储引擎

### MyISAM 存储引擎

### MEMORY存储引擎

### 如何选择存储引擎



## MySQL 数据类型



### 数字类型

MySQL 支持所有标准 SQL 数值数据类型。这些类型包括严格数值数据类型(INTEGER、SMALLINT、DECIMAL 和 NUMERIC)，以及近似数值数据类型(FLOAT、REAL 和 DOUBLE PRECISION)。关键字INT是INTEGER的同义词，关键字DEC是DECIMAL的同义词。BIT数据类型保存位字段值，并且支持 MyISAM、MEMORY、InnoDB 和 BDB表。作为 SQL 标准的扩展，MySQL 也支持整数类型 TINYINT、MEDIUMINT 和 BIGINT。下面的表显示了需要的每个整数类型的存储和范围。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\整数数据类型.png)



### 字符串类型

字符串类型指CHAR、VARCHAR、BINARY、VARBINARY、BLOB、TEXT、ENUM和SET。该节描述了这些类型如何工作以及如何在查询中使用这些类型。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串数据类型.png)

**注意：**char(n) 和 varchar(n) 中括号中 n 代表字符的个数，并不代表字节个数，比如 CHAR(30) 就可以存储 30 个字符。CHAR 和 VARCHAR 类型类似，但它们保存和检索的方式不同。它们的最大长度和是否尾部空格被保留等方面也不同。在存储或检索过程中不进行大小写转换。BINARY 和 VARBINARY 类似于 CHAR 和 VARCHAR，不同的是它们包含二进制字符串而不要非二进制字符串。也就是说，它们包含字节字符串而不是字符字符串。这说明它们没有字符集，并且排序和比较基于列值字节的数值值。BLOB 是一个二进制大对象，可以容纳可变数量的数据。有 4 种 BLOB 类型：TINYBLOB、BLOB、MEDIUMBLOB 和 LONGBLOB。它们区别在于可容纳存储范围不同。有 4 种 TEXT 类型：TINYTEXT、TEXT、MEDIUMTEXT 和 LONGTEXT。对应的这 4 种 BLOB 类型，可存储的最大长度不同，可根据实际情况选择。



### 日期和时间类型

表示时间值的日期和时间类型为DATETIME、DATE、TIMESTAMP、TIME和YEAR。每个时间类型有一个有效值范围和一个"零"值，当指定不合法的MySQL不能表示的值时使用"零"值。TIMESTAMP类型有专有的自动更新特性，将在后面描述。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期和时间数据类型.png)



### 特殊类型（SET 和 ENUM）

特殊类型（SET 和 ENUM）的介绍如下。

|            类型             | 最大值 |                  说明                   |
| :-------------------------: | :----: | :-------------------------------------: |
| Enum("value1","value2",...) | 65535  | 该类型的列只可以容纳所列值之一或为 NULL |
| Set("value1","value2",...)  |   64   |    该类型的列可以容纳一组值或为 NULL    |





# 第六章       操作数据表



## 创建数据表

创建数据表使用 CREATE TABLE 语句。语法如下。

```mysql
CREATE [TEMPORARY] TABLE [IF NOT EXISTS] 数据表名
[(create_definition,...)][table_options][select_statement]
```

CREATE TABLE 语句的参数说明如下所示。

|      关键字       | 说明                                                         |
| :---------------: | :----------------------------------------------------------- |
|     TEMPORARY     | 如果使用该关键字，表示创建一个临时表                         |
|   IF NOT EXISTS   | 该关键字用于避免表存在时 MySQL 报告的错误                    |
| create_definition | 这是表的列属性部分。MySQL 要求在创建表时，表要至少包含一列   |
|   table_options   | 表的一些特性参数，其中大多数选项涉及的是表数据如何存储及存储在何处，如 ENGINE 选项用于定义表的存储引擎。多数情况下，用户不必指定表选项 |
| select_statement  | SELECT 语句描述部分，用它可以快速创建表                      |

下面介绍列属性 create_definition 部分，每一列定义的具体格式如下。

```mysql
col_name type [NOT NULL|NULL] [DEFAULT default_value] [AUTO_INCREMENT]
              [PRIMARY KEY] [reference_definition]
```

属性 create_definition 的参数说明如表。

|         参数          | 说明                                                         |
| :-------------------: | ------------------------------------------------------------ |
|       col_name        | 字段名                                                       |
|         type          | 字段类型                                                     |
|    NOT NULL\|NULL     | 指出该列是否允许是空值，系统一般默认允许为空值，所以当不允许为空值时，必须使用 NOT NULL |
| DEFAULT default_vlaue | 表示默认值                                                   |
|    AUTO_INCREMENT     | 表示是否自动编号，每个表只能有一个 AUTO_INCREMENT 列，并且必须被索引 |
|      PRIMARY KEY      | 表示是否为主键。一个表只能有一个 PRIMARY KEY。如表中没有一个 PRIMARY KEY ，而某些应用程序需要 PRIMARY KEY，MySQL 将返回第一个没有任何 NULL 列的UNIQUE 键，作为 PRIAMRY KEY |
| reference_definition  | 为字段添加注释                                               |

以上是创建一个数据表的一些基本知识，它看起来十分复杂，但在实际的应用中使用最基本的格式创建数据表即可，具体代码如下。

```mysql
CREATE TABLE 数据表名 （列名1 属性，列名2，属性...）
```

使用 CREATE TABLE 语句在 MySQL 数据库 db_admin 中创建一个名为 tb_admin 的数据表，该表包括 id 、user、password 和 createtime 等字段，具体代码如下。

````mysql
USE db_admin;
CREATE TABLE tb_admin(
    id int auto_increment primary,
    user varchar(30) not null,
    password varchar(30) not null,
    createtime datetime);
````

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建数据表.png)



## 查看表结构



### 使用 SHOW COLLUMNS 语句查看

在 MySQL 中，使用 SHOW COLUMNS 语句可以查看表结构，SHOW COLUMNS 语句的基本语法格式如下。

```mysql
SHOW [FULL] COLUMNS FROM 数据表名 [FROM 数据库名];
或
SHOW [FULL] COLUMNS FROM 数据表名.数据库名;
```

使用 SHOW COLUMNS 语句查看数据表 tb_admin 的表结构，具体代码如下。

```mysql
SHOW COLUMNS FROM tb_admin FROM db_admin;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查看数据表结构.png)



### 使用 DESCRIBE 语句查看

在 MySQL 中，还可以使用 DESCRIBE 语句查看数据表结构。DESCRIBE 语句的基本语法格式如下。

```mysql
DESCRIBE 数据表名;
```

其中，DESCRIBE 可以简写成 DESC。在查看表结构时，也可以只列出某一列的信息。其语法格式如下。

```mysql
DESCRIBE 数据表名 列名;
```

使用 DESCRIBE 语句的简写形式查看数据表 tb_admin 中的某一列信息。

```mysql
USE db_admin1;
DESC tb_admin user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查看数据表某列信息.png))



修改表结构使用 ALTER TABLE 语句，修改表结构指增加或删除字段、修改字段名称或者字段类型、设置取消主键外键、设置取消索引以及修改表的注释等，语法如下。

```mysql
ALTER [IGNORE] TABLE 数据表名 alter_spec[,alter_spec]...| table_options
```

参数说明如下。

（1）[IGNORE]：可选项，表示如果出现重复关键的行，则只执行一次，其他重复的执行被删除。

（2）数据表名：用于指定要修改的数据表的名称。

（3）alter_spec子句：用于定义要修改的内容，其语法格式如下。

```mysql
ADD [COLUMN] create_definition [FIRST|AFTER column_name]          //添加新字段
ADD INDEX [index_name] (index_col_name,...)                       //添加索引名称
ADD PRIMARY KEY (index_col_name,...)                              //添加主键名称
ADD UNIQUE [index_name] (index_col_name,...)                      //添加唯一索引
ALTER [COLUMN] col_name {SET DEFAULT literal | DROP DEFAULT}      //修改字段默认值
CHANGE [COLUMN] old_col_name create_definition                    //修改字段名/类型
MODIFY [COLUMN] create_definition                                 //修改字句定义的类型
DROP [COLUMN] col_name                                            //删除字段名称
DROP PRIMARY KEY                                                  //删除主键名称
DROP INDEX index_name                                             //删除索引名称
RENAME [AS] new_tbl_name                                          //更改表名
```

上面的语法中，各参数说明如下。

（1）create_definition：用于定义列的数据类型和属性。

（2）[FIRST | AFTER column_name]：用于指定位于那个字段前面或者后面，当使用 FIRST 关键字时，表示位于指定字段的前面；

使用 AFTER 关键字时，表示位于指定字段的后面。其中的 column_name 表示字段名。

（3）[index_name]：可选项，用于指定索引名。

（4）（index_col_name,...)：用于指定索引列名。

（5）{SET DEFAULT literal | DROP DEFAULT} 子句：为字段设置或者删除默认值。其中 literal 参数为要设置的默认值。

（6）old_col_name：用于指定要修改的字段名。

（7）new_tbl_name：用于指定新的表名。

（8）table_options：用于指定表的一些特性参数，其中大多数选项涉及的是表数据如何存储及存储在何处，如 ENGINE 选项用于定义表的存储引擎。多数情况下，用户不必指定表选项。



### 添加新字段及修改字段定义

在 MySQL 的 ALTER TABLE 语句中，可以通过使用 ADD [COLUMN] create_definition [FIRST | AFTER column_name] 子句来添加新字段；使用 MODIFY [COLUMN] create_definition 字句可以修改已定定义的字段。下面实现向数据表 tb_admin 中添加一个新字段，并修改字段 user 的类型，具体代码如下。

```mysql
ALTER TABLE tb_admin ADD email varchar(50) not null,
modify user varchar(40);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\添加新字段及修改字段定义.png)

通过 DESC 命令查看数据 tb_admin 的表结构，以表查看结构是否成功修改，具体代码如下。

```mysql
DESC tb_admin;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\Desc.png)



### 修改字段名

在 MySQL 的 ALTER TABLE 语句中，使用 CHANGE [COLUMN] old_col_name create_definition 子句可以修改字段名称或者字段类型。下面将数据表 tb_admin 的字段名 user 修改为 username，具体代码如下。

```mysql
ALTER TABLE db_admin1.tb_admin
CHANGE COLUMN user username VARCHAR(30) NULL DEFAULT NULL;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\修改字段名.png)



### 删除字段

在 MySQL 的 ALTER TABLE 中，使用 DROP [COLUMN] col_name 字句可以删除指定字段。下面将数据库 db_admin1 中的数据表 tb_admin 中的字段 email 删除，具体代码如下。

```mysql
ALTER TABLE tb_admin DROp email;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\删除字段.png)



### 修改表名

在 MySQL 的 ALTER TABLE 中，使用 RENAME [AS] new_tbl_name 子句可以修改表名。下面将数据库 db_admin1 中的数据表 tb_admin 更名为 tb_admins，具体代码如下。

```mysql
ALTER TABLE tb_admin RENAME AS tb_admins;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\修改表名.png)



## 重命名表

在 MySQL 中，重命名数据表可以使用 RENAME TABLE 语句来实现。RENAME TABLE 语句的基本语法格式如下。

```mysql
RENAME TABLE 数据表名 1 TO 数据表名 2
```

使用 RENAME 语句对数据表 tb_admins 进行重命名，更名后的数据表为 tb_user，具体代码如下。

```mysql
RENAME TABLE tb_admins TO tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\重命名表.png)



## 复制表

创建表的 CREATE TABLE 命令还有另外一种语法结构，在一张已经存在的数据表的基础上创建一份该表的备份，也就是复制表。这种用法的语法格式如下。

```mysql
CREATE TABLE [IF NOT EXISTS] 数据表名
       {LIKE 源数据表名 | (LIKE 源数据表名)}
```

参数说明如下。

（1）[IF NOT EXISTS]：可选项，如果使用该子句，表示当要创建的数据表名不存在时，才会创建。如果不是用该子句，当要创建的数据表名存在时，将出现错误。

（2）数据表名：表示新创建的数据表的名，该数据表名必须是当前数据库中不存在的表名。

（3）{LIKE 源数据表名 | (LIKE 源数据表名)}：必选项，用于指定依照那个数据表来创建新表，也就是要为那个数据表创建副本。

在数据库 db_admin1 中创建一份数据表 tb_user 的备份 tb_userNew。具体代码如如下。

```mysql
CREATE TABLE tb_userNew
       LIKE tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\备份表.png)

通过查看数据表 tb_user 和 tb_userNew 的表结构可以发现是一样的。但是分别查看数据表的内容，会发现，复制表时并没有复制数据。

如果在复制数据表时，想要同时复制其中的内容，那么需要使用下面的代码来实现。

```mysql
CREATE TABLE tb_userNew1
       AS SELECT * FROM tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\备份表并复制数据.png)



## 删除表

删除数据表的操作很简单，同时删除数据库的操作类似，使用 DROP TABLE 语句即可实现。DROP TABLE　语句的基本语法格式如下。

```mysql
DROP TABLE [IF EXISTS] 数据表名;
```

参数水命如下。

（1）[IF EXISTS]：可选项，用于在删除表前先判断是否存在要删除的表，只有存在时，才会执行删除操作，这样可以避免要删除的表不存在时出现的错误信息。

（2）数据表名：用于指定要删除的数据表名，可以同时删除多张数据表，多个数据表名之间用英文半角的逗号 ”,“ 分隔。

删除数据表 tb_userNew1 具体代码如如下。

```mysql
DROP TABLE tb_userNew1;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\删除表.png)





# 第七章       MySQL 基础



## 运算符



### 算术运算符

算术运算符是 MySQL 中最常用的一类运算符。MySQL 支持的算术运算符包括加、减、乘、除、求余。如表所示。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\算术运算符.png)



### 比较运算符

比较运算符是查询数据时最常用的一类运算符。SELECT 语句中条件语句经常要使用比较运算符。通过这些比较运算符，可以判断表中的那些记录是符合条件的。比较运算符的符号、名称和应用，如表所示。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\比较运算符.png)

比较运算符，真就返回1，假则返回0；

（1）运算符 “=”

```mysql
select id,username,id=1 from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\运算符等于号.png)

（2）运算符 “<>” 和 “!=”（真就返回1，假则返回0，NULL返回NULL）

```mysql
select id,username,password<>222,password!=222,password!=333 from tb_user where id=1;
```

（3）运算符 “>”（真就返回1，假则返回0，NULL返回NULL）

```mysql
select id,username,password>555 from tb_user;
```

（4）运算符 IS NULL（判断是否为空，真就返回1，假则返回0）

```mysql
select id,username,password IS NULL from tb_user;
```

（5）运算符 BETWEEN AND（真就返回1，假则返回0，NULL返回NULL）

```mysql
表达式：x1 BETWEEN m AND n
select password,password BETWEEN 100 AND 555,password BETWEEN 556 AND 999 from tb_user;
```

（6）运算符 IN（真就返回1，假则返回0，NULL返回NULL）

```mysql
表达式：x1 IN(值1,值2,...,值n)
select password,password IN(111,555,999) from tb_user;
```

（7）运算符 LIKE（真就返回1，假则返回0，NULL返回NULL）

```mysql
表达式：x1 LIKE s1
select username,username like 'an',username like '%i%' from tb_user;
```

（8）运算符 REGEXP（真就返回1，假则返回0，NULL返回NULL）

```mysql
x1 REGEXP '匹配方式'
select username,username REGEXP 'a',username REGEXP 'i',username REGEXP 'n' from tb_user;
```



### 逻辑运算符

逻辑运算符用来判断表达式的真假。如果表达式是真，结果返回1；如果表达式是假，结果返回0。逻辑运算符又称为布尔运算符。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\逻辑运算符.png)



### 位运算符

位运算符是在二进制上进行计算的运算符。位运算会先将操作数变成二进制数再进行位运算，然后再将计算结果从二进制数变回十进制数。如果表达式是真，结果返回1；如果表达式是假，结果返回0。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\位运算符.png)



### 运算符的优先级

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\运算符的优先级.png)



## 流程控制语句



### IF 语句

IF 语句用来进行条件判断，根据不同的条件执行不同的操作。该语句在执行时首先判断 IF 后的条件是否为真，则执行 THEN 后的语句，如果为假则继续判断 IF 语句直到为真为止，当以上都不满足时则执行 ELSE 语句后的内容。IF 语句表示形式如下。

```mysql
IF condition THEN
...
[ELSE condition THEN]
...
[ELSE]
...
ENDIF
```

示例

```mysql
delimiter //
create procedure example_if(in x int)
begin
if x=1 then select 1;
elseif x=2 then select 2;
else select 3;
end if;
end
//
>>>>>>>>>>>>>>>>>
通过 MySQL 调用该存储过程。
call example_if(2)//
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\IF语句.png)

### CASE 语句

CASE 语句为 多分支语句结构，该语句首先从 WHEN 后的 VALUE 中查找与 CASE 后的 VALUE 相等的值，如果查找到则执行该分支的内容，否则执行 ELSE 后的内容。CASE 语句表示形式如下。

```mysql
CASE value
     WHEN value THEN...
     [WHEN value THEN...]
     [ELSE...]
END CASE
```

其中，value 参数表示条件判断的变量；WHEN ...THEN 中的 value 参数表示变量的取值。CASE 语句另一种语法表示形式如下。

```mysql
CASE
     WHEN value THEN...
     [WHEN value THEN...]
     [ELSE...]
END CASE
```

示例

```mysql
delimiter //
create procedure example_case(in x int)
begin
case x
when 1 then select 1;
when 2 then select 2;
else select 3;
end case;
end
//
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CASE语句.png)



### WHILE 循环语句

WHILE 循环语句执行时首先判断 condition 条件是否为真，如果是则执行循环体，否则退出循环。该语句表示形式如下。

```mysql
WHILE condition DO
...
END WHILE;
```

示例

```mysql
delimiter //
create procedure example_while(out sum int)
begin
declare i int default 1;
declare s int default 0;
while i<=100 do
set s=s+i;
set i=i+1;
end while;
set sum=s;
end
//
调用该存储过程，调用语句如下所示。
call example_while(@s)//
select @s//
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\WHILE语句.png)



### LOOP 循环语句

该循环没有内置的循环条件，但可以通过 LEAVE 语句退出循环。LOOP 语句表示形式如下。

```mysql
LOOP
...
END LOOP
```

LOOP 允许某特定语句或语句群的重复执行，实现一个简单的循环构造，中间省略的部分是需要重复执行的语句。在循环内的语句一直重复直至循环被退出，退出循环应用 LEAVE 语句。LEAVE 语句经常和 BEGIN ... END 或循环一起使用，其表示形式如下。

```mysql
LEAVE label
```

label 是语句中标注的名字，这个名字是自定义的。加上 LEAVE 关键字就可以用来退出被标注的循环语句。示例如下。

```mysql
delimiter //
create procedure example_loop(out sum int)
begin
declare i int default 1;
declare s int default 0;
loop_label:loop
set s=s+i;
set i=i+1;
if i>100 then 
leave loop_label;
end if;
end loop;
set sum=s;
end
//
调用名称为 example_loop 的存储过程，其代码如下。
call example_loop(@s)//
select @s//
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\LOOP循环语句.png)



### REPEAT 循环语句

该语句先执行一次循环体，之后判断 condition 条件是否为真，为真则退出循环，否则继续执行循环。REPEAT 语句表示形式如下。

```mysql
REPEAT
...
UNTIL condition
END REPEAT
```

示例

```mysql
delimiter //
create procedure example_repeat(out sun int)
begin
declare i int default 1;
declare s int default 0;
repeat
set s=s+i;
set i=i+1;
until i>100
end repeat;
set sun=s;
end
//
调用名称为 example_loop 的存储过程，其代码如下。
call example_repeat(@s)//
select @s//
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\REPEAT循环语句.png)

循环语句中还有一个 ITERATE 语句，它可以出现在 LOOP、REPEAT 和 WHILE 语句内，其意为“再次循环”。该语句格式如下。

```mysql
ITERATE label
```

该语句的格式与 LEAVE 大同小异，区别在于：LEAVE 语句是离开一个循环，而 ITERATE 语句是重新开始一个循环。





# 第八章       表数据的增、删、改操作



## 插入数据



### 使用 INSERT ... VALUES 语句插入数据

使用 INSERT ... VALUES 语句插入数据，是 INSERT 语句的最常用的语法格式。它的语法格式如下。

```mysql
INSERT [LOW PRIORITY | DEFAULT | HIGH_PRIORITY] [IGNORE]
       [INTO] 数据表名 [(字段名,...)]
       VALUES ({值 | DEFAULT},...),(...),...
       [ON DUPLICATE KEY UPDATE 字段名=表达式,...]
```

参数说明如下。

（1）[LOW_PRIORITY | DELAYED | HIGH_PRIORITY]：可选项，其中，LOW_PRIORITY 是 INSERT、UPDATE 和 DELETE 语句都支持的一种可选修饰符，通常应用在多用户访问数据库的情况下，用于指示 MySQL 降低 INSERT、DELETE 或 UPDATE 操作执行的优先级；DELAYED 是 INSERT 语句支持的一种可选修饰符，用于指定 MySQL 服务器把待插入的行数据放到一个缓冲器中，直到待插数据的表空闲时，才真正在表中插入数据行；HIGH_PRIORITY 是 INSERT 和 SELECT 语句支持的一种可选修饰符，用于指定 INSERT 和 SELECT 操作优先执行的。

（2）[IGNORE]：可选项，表示在执行 INSERT 语句时，所出现的错误都会被当作警告处理。

（3）[INTO ]数据表名：可选项，用于指定被操作的数据表。

（4）[(字段名,...)]：可选项，当不指定该选项时，表示要向表中所有列插入数据，否则表示向数据表的指定列插入数据。

（5）VALUES({值 | DEFAULT},...),(...),...：必选项，用于指定需要插入的数据清单，其顺序必须与字段的顺序相对应。其中的每一列的数据可以是一个常量、变量、表达式或者 NULL，但是其数据类型要与相应的字段类型相匹配；也可以直接使用 DEFAULT 关键字，表示为该列插入默认值，但是使用的前提是已经明确指定了默认值，否则会出错。

（6）ON DUPLIVCATE KEY UPDATE 子句：可选项，用于指定向表中插入行时，如果导致 UNIQUE KEY 或 PRIMARY KRY 出现重复值，系统会根据 UPDATE 后的语句修改表中原有行数据。



INSERT...VALUES 语句在使用时，通常有以下3种方式。

**插入完整数据**

通过 INSERT...VALUES 语句向数据表 tb_user 中插入一条完整的数据，具体代码如下。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\插入完整数据.png)

**插入数据记录的一部分**

通过 INSERT...VLAUES 语句还可以实现向数据表中插入数据记录的一部分，也就是只插入表的一行中的某几个字段的值，下面向数据表 tb_user 中插入数据记录的一部分。只包括 user 和 password 字段的值，具体代码如下。

```mysql
INSERT INTO tb_user (user,password)
       VALUES('zhangsan','111');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\插入数据记录的一部分.png)

**插入多条记录**

通过 INSERT VALUES 语句还可以实现一次性插入多条记录，下面向数据表 tb_user 中插入3条记录，都只包括 username、password 和 createtime 字段的值，具体代码如下。

```mysql
INSERT INTO tb_user (username,password,createtime)
       VALUES('lisi','777','2021-04-05 10:10:10'),
       ('wangwu','877','2021-04-05 10:10:10'),
       ('zhaoliu','797','2021-04-05 10:10:10');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\插入多条记录.png)



### 使用 INSERT...SET 语句插入数据

在 MySQL 中，除了可以使用 INSERT...VALUES 语句插入数据外，还可以使用 INSERT...SET 语句插入数据。这种语法格式用于通过直接给表的某些字段指定对应的值来实现插入指定数据，对于未指定值的字段将采用默认值进行添加。INSERT...SET 语句语法格式如下。

```mysql
INSERT [LOW_PRIORITY | DELAYED | HIGH_PRIORITY] [IGNORE]
    [INTO] 数据表名
    SET 字段名={值 | DEFAULT},...
    [ON DUPLICATE KEY UPDATE 字段名=表达式,...]
```

参数说明如下。

（1）[LOW_PRIORITY | DELAYED | HIGH_PRIORITY]：可选项，其中，LOW_PRIORITY 是 INSERT、UPDATE 和 DELETE 语句都支持的一种可选修饰符，通常应用在多用户访问数据库的情况下，用于指示 MySQL 降低 INSERT、DELETE 或 UPDATE 操作执行的优先级；DELAYED 是 INSERT 语句支持的一种可选修饰符，用于指定 MySQL 服务器把待插入的行数据放到一个缓冲器中，直到待插数据的表空闲时，才真正在表中插入数据行；HIGH_PRIORITY 是 INSERT 和 SELECT 语句支持的一种可选修饰符，用于指定 INSERT 和 SELECT 操作优先执行的。

（2）[INTO ]数据表名：可选项，用于指定被操作的数据表，可以省略。

（3）SET 字段名={值 | DEFAULT}：用于给数据表中的某些字段设置要插入的值。

（4）ON DUPLIVCATE KEY UPDATE 子句：可选项，用于指定向表中插入行时，如果导致 UNIQUE KEY 或 PRIMARY KRY 出现重复值，系统会根据 UPDATE 后的语句修改表中原有行数据。

通过 INSERT...SET 语句向数据表 tb_user中插入一条记录，包括 username、password 和 createtime 字段的值，具体代码如下。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\使用INSERT_SET语句插入数据.png)



### 插入查询结果

在 MySQL 中，支持将查询结果插入到指定的数据表中，这可以通过 INSERT...SELECT 语句来实现。

```mysql
INSERT [LOW_PRIORITY | HIGH_PRIORITY] [IGNORE]
     [INTO] 数据表名 [(字段名,...)]
     SELECT ...
     [ON DUPLIVCATE KEY UPDATE 字段名=表达式,...]
```

参数说明如下。

（1）[LOW_PRIORITY | DELAYED | HIGH_PRIORITY]：可选项，其中，LOW_PRIORITY 是 INSERT、UPDATE 和 DELETE 语句都支持的一种可选修饰符，通常应用在多用户访问数据库的情况下，用于指示 MySQL 降低 INSERT、DELETE 或 UPDATE 操作执行的优先级；DELAYED 是 INSERT 语句支持的一种可选修饰符，用于指定 MySQL 服务器把待插入的行数据放到一个缓冲器中，直到待插数据的表空闲时，才真正在表中插入数据行；HIGH_PRIORITY 是 INSERT 和 SELECT 语句支持的一种可选修饰符，用于指定 INSERT 和 SELECT 操作优先执行的。

（2）[INTO ]数据表名：可选项，用于指定被操作的数据表，可以省略。

（3）[(字段名,...)]：可选项，当不指定该选项时，表示要向表中所有列插入数据，否则表示向数据表的指定列插入数据。

（4）SELECT 子句：用于快速地从一个或者多个表中取出数据，并将这些数据作为行数据插入到目标数据表中。需要注意的是，SELECT 字句返回的结果集中的字段数、字段类型必须与目标数据表完全一致。

（5）ON DUPLIVCATE KEY UPDATE 子句：可选项，用于指定向表中插入行时，如果导致 UNIQUE KEY 或 PRIMARY KRY 出现重复值，系统会根据 UPDATE 后的语句修改表中原有行数据。

下面实现从数据表 tb_user 中查询 username、password 和 createtime 字段的值，插入到数据表 tb_usernew 中，具体代码如下。

```mysql
INSERT INTO tb_usernew
    (username,password,createtime)
    SELECT username,password,createtime FROM tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\插入查询结果.png)



## 修改数据

要执行修改的操作可以使用 UPDATE 语句，语法如下。

```mysql
UPDATE [LOW_PRIORITY] [IGNORE] 数据表名
    SET 字段1=值1 [,字段2=值2 ...]
    [WHERE 条件表达式]
    [ORDER BY...]
    [LIMIT 行数]
```

参数说明如下。

（1）[LOW_PRIORITY]：可选项，表示再多用户访问数据库的情况下可用于延迟 UPDATE 操作，直到没有别的用户再从表中读取数据为止。这个过程仅适用于表级锁的存储引擎（如 IyISAM、MEMORY 和 MERGE）。

（2）[IGNORE]：在 MySQL 中，通过 UPDATE 语句更新表中的多行数据时，如果出现错误，那么整个 UPDATE 语句操作都会被取消，错误发生前更新的所有行将被恢复到它们原来的值。因此在发生错误时也要继续进行更新，则可以在 UPDATE 语句中使用 IGNORE 关键字。

（3）SET 子句：必选项，用于指定表中要修改的字段名及其字段值。其中的值可以是表达式，也可以是该字段所对应的默认值。如果指定默认值，那么使用关键字 DEFAULT 指定。

（4）WHERE 子句：可选项，用于限定表中要修改的行，如果不指定该子句，那么 UPDATE 语句会更新表中的所有行。

（5）ORDER BY 子句：可选项，用于限定表中的行被修改的次序。

（6）LIMIT 子句：可选项，用于限定被修改的行数。

下面将管理员信息表 tb_user 中的用户名为 zhangsan 的管理员密码111改为123。具体代码如下。

```mysql
UPDATE db_admin1.tb_user SET password='123' WHERE username='zhangsan';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\修改数据.png)



## 删除数据

在数据库中，有些数据已经失去意义或者错误时就需要将它们删除，在 MySQL 中，可以使用 DELETE 语句或者 TRUNCATE TABLE 语句删除表中的一行或多行数据，下面分别进行介绍。

### 通过 DELETE 语句删除数据

通过 DELETE 语句删除数据的基本语法格式如下。

```mysql
DELETE [LOW_PRIORITY] [QUICK] [IGNORE] FROM 数据表名
     [WHERE 条件表达式]
     [ORDER BY...]
     [LIMIT 行数]
```

参数说明如下。

（1）[LOW_PRIORITY]：可选项，表示再多用户访问数据库的情况下可用于延迟 UPDATE 操作，直到没有别的用户再从表中读取数据为止。这个过程仅适用于表级锁的存储引擎（如 IyISAM、MEMORY 和 MERGE）。

（2）[QUICK] 子句：可选项，用于加快部分种类的删除操作的速度。

（3）[IGNORE]：在 MySQL 中，通过 DELETE 语句删除表中的多行数据时，如果出现错误，那么整个 DELETE 语句操作都会被取消，错误发生前更新的所有行将被恢复到它们原来的值。因此在发生错误时也要继续进行更新，则可以在 DELETE 语句中使用 IGNORE 关键字。

（4）WHERE 子句：可选项，用于限定表中要删除的行，如果不指定该子句，那么 DELETE 语句会删除表中的所有行。

（5）ORDER BY 子句：可选项，用于限定表中的行被删除的次序。

（6）LIMIT 子句：可选项，用于限定被删除的行数。

删除管理员数据表 tb_user 中用户名为 wangwu 的记录信息。具体代码如下。

```mysql
DELETE FROM tb_user WHERE username='wangwu'
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\通过DELETE语句删除数据.png)



### 通过 TRUNCATE TABLE 语句删除数据

在删除数据时，如果要从数据表中删除所有的行，通过 TRUNCATE TABLE 语句删除数据的基本语法格式如下。

```mysql
TRUNCATE [TABLE] 数据表名
```

使用 TRUNCATE TABLE 语句清空管理员数据表 tb_usernew，具体代码如下。

```mysql
TRUNCATE TABLE db_admin1.tb_usernew;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\通过TURNCATE_TABLE语句删除数据.png)

DELETE 语句与 TRUNCATE TABLE 语句的区别如下。

（1）使用 TRUNCATE TABLE 语句后，表中的 AUTO_INCREMENT 计数器将被重新设置为该列的初始值。

（2）对于参与了索引和视图的表，不能使用 TRUNCATE TABLE 语句来删除数据，而应用使用 DELETE 语句。

（3）TRUNCATE TABLE 操作与 DELETE 操作使用的系统和事务日志资源少。DELETE 语句每删除一行都会在事务日志中添加一行记录，而 TRUNCATE TABLE 语句时通过释放存储表数据所用的数据页来删除数据的，因此只在事务日志中记录页的释放。



# 第九章     数据查询



## 基本查询语句

SELECT 语句是最常用的查询语句，他的使用方式有些复杂，但功能是相当强大的。SELECT 语句的基本语法如下。

```mysql
select selection_list             //要查询的内容，选择那些列
from 数据表名                      //指定数据表
where primary_constraint          //查询时需要满足的条件，行必须满足的条件
group by grouping_columns         //如何对结果进行分组
order by sorting_columns          //如何对结果进行排序
having secondary_constraint       //查询时满足的第二条件
limit count                       //限定输出的查询结果
```



**使用 SELECT 语句查询一个数据表**

使用 SELECT 语句时，首先要确定所要查询的列。“ * ” 代表所有的列。例如，查询 db_admin1 数据库 tb_user 表中的所有数据，代码如下。

```mysql
select * from tb_user;
```

**查询表中的一列或多列**

针对表中的多列进行查询，只要在 select 后面指定要查询的列名即可，多列之间用 “，”分隔。例如，查询 tb_user 表中的 id 和 username，代码如下。

```mysql
select id, username from tb_user;
```



## 单表查询



### 查询所有字段

查询所有字段是指查询表中所有字段的数据。这种方式可以将表中所有字段的数据都查询出来。在 MySQL 中可以使用 “ * ” 代表所有的列，即可查出的所有字段，语法格式如下。

```mysql
SELECT * FROM 表名;
```



### 查询指定字段

查询指定字段可以使用下面的语法格式。

```mysql
SELECT 字段名 FROM 表名;
```

查询 db_user 数据库 tb_user 表中 username 和 password 两个字段，SELECT 查询语句语法如下。

```mysql
SELECT username,password FROM tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查询指定字段.png)



### 查询指定数据

如果要从很多记录中查询出指定的记录，那么就需要一个查询的条件.设定查询条件应用的是 WHERE 子句。通过它可以实现很多复杂的条件查询。在使用 WHERE 子句时，需要使用一些比较运算符来确定查询的条件。其常用的比较运算符如表所示。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\比较运算符.png)

应用 WHERE 子句 查询 tb_user 表，条件是 username 为 zhangsan，代码如下。

```mysql
select * from tb_user where username="zhangsan";
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查询指定数据.png)



**带关键字 IN 的查询**

关键字 IN 可以判断某个字段的值是否在指定的集合中。如果字段的值在集合中，则满足查询条件，该记录将被查询出来；如果不在集合中，则不满足查询条件。其语法格式如下。

```mysql
SELECT * FROM 表名 WHERE 条件 [NOT] IN (元素1,元素2,元素3,...,元素n);
```

（1）[NOT]：是可选项，加上 NOT 表示不在集合内满足条件；

（2）元素：表示集合中的元素，各元素之间用逗号隔开，字符型元素需要加上单引号。

应用 IN 关键字查询 tb_user 表中 username 字段为 zhangsan 和 lisi 的记录，查询语句如下。

```mysql
SELECT * FROM tb_user WHERE username IN ('zhangsan','lisi');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字IN的查询.png)

使用关键字 NOT IN 查询 tb_user 表中 username 字段不为 zhangsan 和 lisi 的记录，查询语句如下。

```mysql
SELECT * FROM tb_user WHERE username NOT IN('zhangsan','lisi');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字NOT_IN的查询.png)



**带关键字 BETWEEN AND 的范围查询**

关键字 BETWEEN AND 可以判断某个字段的值是否在指定的范围之内。如果字段的值在指定范围内，则满足查询条件，该记录将被查询出来。如果不在指定范围内，则不满足查询条件。其语法如下。

```mysql
SELECT * FROM 表名 WHERE 条件 [NOT] BETWEEN 取值1 AND 取值2;
```

（1）[NOT]：可选项，表示不再指定范围内满足条件。

（2）取值 1：表示范围的起始值。

（3）取值2：表示范围的终止值。

查询 tb_user 表中 id 值在1~10之间的数据，查询语句如下。

```mysql
SELECT * FROM tb_user WHERE id BETWEEN 1 AND 10;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字BETWEEN_AND的范围查询.png)

如果要查询 tb_user 表中 id 值不在1~10之间的数据，则可以通过 NOT BETWEEN AND 来完成。其查询语法如下。

```mysql
SELECT * FROM tb_user WHERE id NOT BETWEEN 1 AND 10;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字NOT_BETWEEN_AND的范围查询.png)



### 带 LIKE 的字符匹配查询

LIKE 属于较常用的比较运算符，通过它可以实现模糊查询。它有两种通配符：“ % ” 和下划线 “ _ ”。

（1）“ % ” 可以匹配一个或多个字符，可以代表任意长度的字符串，长度可以为0.例如，“明%技” 表示以 “ 明 ” 开头，以 “ 技 ” 结尾的任意长度的字符串。该字符串可以代表 “ 明日科技 ” “明日百编程科技” “明日图书科技” 等字符串。

（2）“ _ ” 只匹配一个字符。例如，m_n 表示以 m 开头，以 n 结尾的三个字符。中间的 “ _ ” 可以代表任意一个字符。

查询 tb_user 表中 user 字段中包含 a 字符的数据，查询语句如下。

```mysql
select * from tb_user where username like '%a%';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带LIKE的字符匹配查询.png)



### 用关键字 IS NULL 查询空值

关键字 IS NULL 可以用来判断字段的值是否为空值（NULL）。如果字段的值是空值，则满足查询条件，该纪录被查询出来。如果字段的值不为空值，则不满足查询条件。其语法格式如下。

```mysql
IS [NOT] NULL
```

下面使用关键字 IS NULL 查询 tb_user 表中 createtime 字段的值为空值的记录，查询语句如下。

```mysql
SELECT * FROM tb_user WHERE createtime IS NULL;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\用关键字IS_NULL查询空值.png)



### 用关键字 AND 的多条件查询

关键字 AND 可以用来联合多个条件进行查询。使用关键字 AND 时，只有同时满足所有查询条件的记录会被查询出来。如果不满足这些查询条件的其中一个，这样的记录将被排除掉。关键字 AND 的语法格式如下。

```mysql
SELECT * FROM 数据表名 WHERE 条件1 AND 条件2 [...AND 条件表达式n];
```

下面查询数据表 tb_user 中 username 字段值为 zhangsan，并且 password 字段值为 111 的记录，查询语句如下。

```mysql
SELECT * FROM tb_user WHERE username="zhangsan" AND password="111";
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字AND的多条件查询.png)



### 带关键字 OR 的多条件查询

关键字 OR 也可以用来联合多个条件进行查询，但是与关键字 AND 不同，关键字 OR 只要满足查询条件中的一个，那么此记录就会被查询出来；如果不满足这些查询条件中的任何一个，这样的纪录将会被排除掉。关键字 OR 的语法格式如下。

```mysql
select * from 数据表名 where 条件1 OR 条件2 [...OR 条件表达式n];
```

下面查询 tb_user 表中 username 字段的值为 “zhangsan” 或者 “lisi” 的记录，查询语句如下。

```mysql
select * from tb_user where username="zhangsan" OR "lisi";
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字OR的多条件查询.png)



### 带关键字 DISTINCT 去除结果中的重复行

使用关键字 DISTINCT 可以去除查询结果中的重复记录，语法格式如下。

```mysql
select distinct 字段名 from 表名;
```

下面使用关键字 DISTINCT 去除 tb_user 表中 username 字段中的重复记录，查询语句如下。

```mysql
select distinct username from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\用关键字DISTINCT去除结果中的重复行.png)



### 用关键字 ORDER BY 对查询结果排序

使用关键字 ORDER BY 可以对查询的结果进行升序（ASC）和降序（DESC）排列，在默认情况下，ORDER BY 按升序输出结果。如果要按降序排列可以使用 DESC 来实现。语法格式如下。

```mysql
ORDER BY 字段名 [ASC|DESC];
```

（1）ASC 表示按升序进行排序。

（2)DESC 表示按降序进行排序。

查询 tb_user 表中的所有信息，按照 id 序号进行降序排序排列，查询语句如下。

```mysql
select * from tb_user order by id desc;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\用关键字ORDER_BY对查询结果排序.png)



### 用关键字 GROUP BY 分组查询

通过关键字 GROUP BY 可以将数据划分到不同的组中，实现对记录进行分组查询。在查询时，所查询的列必须包含在分组的列中，目的是使查询到的数据没有矛盾。

**（1）使用关键字 GROUP BY 来分组**

使用关键字 GROUP BY 对 tb_user 表中 id 字段进行分组查询，查询语句如下。

```mysql
select id,username,createtime from tb_user GROUP BY id;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\使用关键字GROUP_BY来分组.png)

**（2）关键字 GROUP BY 与 GROUP_CONCAT()** 

下面使用关键字 GROUP BY 和 GROUP_CONCAT()函数对 tb_user 表中的 sex 字段进行分组查询，查询语句如下。

```mysql
select sex,group_concat(username) from tb_user group by sex; 
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\关键字GROUP_BY与GROUP_CONCAT()函数.png)

**按多个字段进行分组**

使用关键字 GROUP BY 也可以按多个字段进行分组。

```mysql
select username,password,sex,id from tb_user group by sex,id;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\按多个字段进行分组.png)



### 用关键字 LIMIT 限制查询结果的数量

查询数据时，可能会查询出很多的纪录，而用户需要的纪录可能只是很少的一部分，这样就需要来限制查询结果的数量。LIMIT 是 MySQL 中的一个特殊关键字。关键字 LIMIT 可以对查询结果的记录条数进行限定，控制它输出的行数。下面通过查询数据表 tb_user 中，按照 id 编号进行升序排列，显示前3条记录，查询语句如下。

```mysql
select * from tb_user order by id asc limit 3;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\用关键字LIMIT限制查询结果的数量.png)

使用关键字 LIMIT 还可以从查询结果的中间部分取值。首先要定义两个参数，参数1是开始读取的第一条记录的编号（在查询结果中，第一个结果的记录编号是0，而不是1）；参数2是要查询记录的个数。查询 tb_user 表中 按 id 编号进行升序排列，从编号1开始，查询两个记录，查询语句如下。

```mysql
select * from tb_user order by id asc limit 1,3;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\关键字LIMIT的两个参数.png)



## 聚合函数查询

聚合函数的最大特点是它们根据一组数据求出一个值。聚合函数的结果值只根据选定行中非 NULL 的值进行计算，NULL 值被忽略。

### COUNT()函数

COUNT()函数，对于除 “ * ” 以外的任何参数，返回所选择集合中非 NULL 值的行的数目；对于参数 “ * ”，返回选择集合中所有行的数目，包括 NULL 值的行。没有 WHERE 子句的 COUNT(*)是经过内部优化的，能够快速返回表中所有的记录总数。下面使用 count()函数统计数据表 tb_user 中的记录数，查询语句如下。

```mysql
select count(*) from tb_user;
select count(createtime) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\COUNT()函数.png)



### SUM()函数

SUM()函数可以求出表中某个字段取值的总和。

使用 SUM()函数统计数据表 tb_user 中 计算 password 字段的总和。下面使用 SUM()函数来查询，查询结果入下。

```mysql
select sum(password) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SUM()函数.png)



### AVG()函数

AVG()函数可以求出表中某个字段取值的平均值。下面使用 AVG()函数求数据表 tb_user 中 password 字段值的平均值，查询语句如下。

```mysql
select AVG(password) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\AVG()函数.png)



### MAX()函数

MAX()函数可以求出表中某个字段取值的最大值。下面使用 MAX()函数查询数据表 tb_user 中 password 字段的最大值，查询语句如下。

```mysql
select MAX(password) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\MAX()函数.png)



### MIN()函数

MIN()函数可以求出表中某个字段取值的最小值。下面使用 MIN()函数查询数据表 tb_user 中 password字段的最小值，查询语句如下。

```mysql
select MIN(password) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\MIN()函数.png)



## 连接查询



### 内连接查询

内连接是最普遍的连接类型，而且是最匀称的，因为它们要求构成连接的每一部分的每个表的匹配，不匹配的行将被排除。内连接的最常见的例子是相等连接，也就是连接后的表中某个字段与每个表中的都相同，这种情况下，最后的结果集只包括参加连接的表中与指定字段相符的行。下面有两个表，tb_user 用户信息表和 borrow 图书借阅表，它们两个表中存在一个相同的 user 字段连接。因此可以创建两个表的一个连接。查询语句如下。

```mysql
select borrow.id,username,bookid from tb_user,borrow where tb_user.id=borrow.id;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\内连接查询.png)



### 外连接查询

与内连接不同，外连接是指使用 OUTER JOIN 关键字将两个表连接起来。外连接生成的结果集不仅包括符合连接条件的行数据，而且还包括左表（左外连接时的表）、右表（右外连接时的表）或两边连接的表（全外连接时的表）中所有的数据行。语法格式如下。

```mysql
SELECT 字段名称 FROM 表名1 LEFT|RIGHT JOIN 表名2 ON 表名1.字段名1=表名2.属性名2;
```

外连接分为左外连接（LEFT JOIN）、右外连接（RIGHT JOIN）和全外连接3种类型。

**（1）左外连接**

左外连接（LEFT JOIN）是指将左表中的所有数据分别与右表中的每一条数据进行连接组合，返回的结果出内连接的数据外，还包括左表不符合条件的数据，并在右表的对应列中添加 NULL 值。下面使用左连接查询 tb_user 表和 borrow 表，通过 id 字段进行连接，查询语句如下。

```mysql
select tb_user.id,username,password,createtime,bookid,borrowtime from tb_user left join borrow on tb_user.id=borrow.id;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\左外连接.png)

**（2）右外连接**

右外连接（RIGHT JOIN）是指将右表中的所有数据分别与左表中的每一条数据进行连接组合，返回的结果出内连接的数据外，还包括右表不符合条件的数据，并在左表的对应列中添加 NULL 值。下面使用右连接查询 tb_user 表和 borrow 表，通过 id 字段进行连接，查询语句如下。

```mysql
select tb_user.id,username,password,createtime,bookid,borrowtime from borrow right join tb_user on tb_user.id=borrow.id;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\右外连接.png)



### 复合条件连接查询

在连接查询时，也可以增加其他的限制条件。通过多个条件的复合查询，可以是查询结果更加准确。下面使用内连接查询 tb_user 表和borrow 表中的 password 字段值必须大于555，查询语句如下。

```mysql
select borrow.id,username,bookid,password from tb_user,borrow where tb_user.id=borrow.id and password>555;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\复合条件连接查询.png)



## 子查询

子查询就是 SELECT 查询是另一个查询的附属。在外面一层的查询中使用里面一层查询产生的结果集。这样就不是执行两个（或者多个）独立的查询，而是执行包含一个（或者多个）子查询的单独查询。

当遇到这样的多层查询时，MySQL 从最内层的查询开始，然后从它开始向外向上移动到外层（主）查询，在这个过程中每个查询产生的结果集都不被赋给包围它的父查询，接着这个父查询被执行，它的结果也被指定给父查询。

除了结果集经常由包含一个或多个值的一列组成外，子查询和常规 SELECT 查询的执行方式一样。子查询可以用在任何可以使用表达式的地方，它必须由父查询包围，而且，如同常规的 SELECT 查询，它必须包含一个字段列表（这是一个单列列表）、一个具有一个或者多个表名字的 FROM 子句以及可选的 WHERE、HAVING 和 GROUP BY。



**带关键字 IN 的子查询**

只有子查询返回的结果列包含一个值时，比较运算符才适用。假如一个子查询返回的的结果集是值的列表，这是比较运算符就必须用关键字 IN 代替。IN 运算符可以检测结果集中是否存在某个特定的值，如果检测成功就执行外部的查询。下面查询 tb_user 表中的记录，但 id字段值必须在 borrow 表中的 id 字段中出现过，查询语句如下。

```mysql
select * from tb_user where id in (select id from borrow);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字IN的子查询.png)

如果 borrow 表中 的字段 id 里没有 tb_user 里的相对应字段 id 的值，则查询不出该记录。



### 带比较运算符的子查询

子查询可以使用比较运算符，包括=、!=、>、>=、< 和 <= 等。比较运算符在子查询时使用非常广泛。下面查询 id 大于1的用户借阅书的字段 bookid，查询语句如下。

```mysql
select id,bookid,borrowid from borrow where id>(select id from tb_user where id=1);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带比较运算符的子查询.png)



**带关键字 EXISTS 的子查询**

使用关键字 EXISTS 时，内层查询与局部返回查询结果的记录。而是返回一个真假值。如果内层查询语句查询到满足条件的记录，就返回一个真值，否则将返回一个假值。当返回的值为 true 时，外层查询语句将进行查询；当返回的值为 false 时，外层查询与局部进行查询或者查询不出任何记录。

下面使用子查询查询 tb_user 表中是否存在 id 值为27的记录，如果存在则查询 tb_user 表中的记录，如果则不执行外层查询，查询语句如下。

```mysql
select * from tb_user where exists(select * from borrow where id=44);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字EXISTS的子查询.png)



### 带关键字 ANY 的子查询

关键字 ANY 表示满足其中任意一个条件。使用关键字 ANY 时，只要满足内层查询语句返回的结果中的任意一个，就可以通过该条件来执行外层查询语句。

查询 tb_user 表中 id 字段的值小于 borrow 表中 id 字段最小值的记录，首先查询出 borrow 表中 id 字段的值，然后使用关键字 ANY（“<ANY”表示小于所有值）判断，查询语句如下。

```mysql
select id,username,password from tb_user where id<ANY(select id from borrow);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字ANY的子查询.png)

补充：

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ANY子查询.png)



### 带关键字 ALL 的子查询

关键字 ALL 表示满足所有条件。使用关键字 ALL 时，只有满足内层查询语句返回的所有结果，才可以执行外层查询语句。

查询 tb_user 表中 id 字段的值大于 borrow 表中 id 字段最大值的记录，首先查询出 borrow 表中 id 字段的值，然后使用关键字 ALL（“>=ALL”表示大于所有值）判断，查询语句如下。

```mysql
select id,username,password from tb_user where id>=ALL(select id from borrow);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\带关键字ALL的子查询.png)



## 合并查询结果

合并查询结果时将多个 SELECT 语句的查询结果合并到到一起。因为某种情况下，需要将几个 SELECT 语句查询出来的结果合并起来显示。合并查询结果使用关键字 UNION 和 UNION ALL。关键字 UNION 时将所有的查询结果合并到一起，然后去除相同记录；而关键字 UNION ALL 则只是简单地将结果合并在一起，下面分别介绍这两种合并方法。

```mysql
select id from tb_user
UNION
select id from borrow;

select id from tb_user
UNION All
select id from borrow;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\合并查询结果.png)



## 定义表和字段的别名

在查询时，可以为表和字段取一个别名，这个别名可以代替其指定的表和字段。为字段和表取别名，能够使查询更加方便，而且可以使查询结果以更加合理的方式显示。



### 为表取别名

当表的名称特别长时，在查询中直接使用表名很不方便，这时可以为表取一个贴切的别名。下面为 tb_user 表取别名为 u，然后查询 tb_user 表中的 username 字段值为 zhangsan 的记录，查询语句如下。

```mysql
select * from tb_user u where u.username='zhangsan';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\为表取别名.png)



### 为字段取别名

当查询数据时，MySQL 会显示每个输出的列的名词。默认情况下，显示的列名是创建表是定义的列名。同样可以为这个列取一个别名。

```mysql
字段名 [AS] 别名
```

下面为 tb_user 表中的 username，password 和 createtime 字段分别取别名为用户名、密码和创建时间，代码如下。

```mysql
select username as '用户名',password as '密码',createtime as '创建时间' from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\为字段取别名.png)



## 使用正则表达式查询

正则表达式是用某种模式去匹配一类字符串的一种方式。正则表达式的查询能力比通配字符的查询能力更加强大，而且更加灵活。在MySQL 中，使用关键字 REGEXP 来匹配查询正则表达式来查询。

```mysql
字段名 REGEXP '匹配方式'
```

 （1）字段名：表示需要查询的字段名称。

（2）匹配方式：表示已哪种方式来进行匹配查询。其支持的模式匹配字符如表所示。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\正则表达式.png)



### 匹配指定字符中的任意一个

使用方括号 ([]) 可以将需要查询字符组成一个字符集。只要记录包括方括号总的任意字符，该记录将会被查询出来。例如，通过 “[abc]" 可以查询包含 a、b 和 c 3个字母中任何一个的记录。下面从 tb_user 表 username 字段中查询包含 c、e 和 o 3个字母中的任意一个的记录。SQL 代码如下。

```mysql
SELECT * FROM tb_user WHERE username REGEXP '[ceo]'; 
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\匹配指定字符中的任意一个.png)



### 使用 ” * ” 和 “ + ” 来匹配多个字符

正则表达式中，” * ” 和 “ + ” 都可以匹配多个该符号之前的字符。但是，“ + ”至少表示一个字符，而” * ” 可以表示0个字符。下面从 tb_user 表 username 字段中查询字母 'a' 之前出现过 'n' 的记录。a+n 表示字母 n 前面至少有一个字母 a。SQL 代码如下：

```mysql
SELECT * FROM tb_user WHERE username REGEXP 'a*n';
SELECT * FROM tb_user WHERE username REGEXP 'a+n';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\使用星号和加号来匹配多个字符.png)



### 匹配以指定的字符开头和结束的记录

正则表达式中，^ 表示字符串的开始位置，$ 表示字符串的结束位置。下面在用户信息表 tb_user 中查找姓名（username）字段中以 z 开头、以 n 结尾的，中间包含六个字符的用户信息，SQL 代码如下。

```mysql
SELECT * FROM tb_user WHERE username REGEXP '^z......n$';
```

<img src="C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\匹配以指定的字符开头和结尾的记录.png"  />





# 第十章       常用函数



## MySQL 函数

MySQL 函数是 MySQL 数据库提供的内置函数。这些内置函数可以帮助用户更加方便地处理表中的数据。MySQL 内置函数类别及作用，如表所示。

|      函数      | 作用                                                         |
| :------------: | ------------------------------------------------------------ |
|    数学函数    | 用于处理数字，这类函数包括绝对值函数，正弦函数、余弦函数和获取随机数函数等。 |
|   字符串函数   | 用于处理字符串。其中包括字符串连接函数。字符串比较函数、字符串中字母大小写转换函数等。 |
| 日期和时间函数 | 用于处理日期和时间。其中包括获取当前时间的函数、获取当前日期的函数、返回年份的函数和返回日期的函数等。 |
|  条件判断函数  | 用于在 SQL 语句中控制条件选择。其中包括 IF 语句、CASE 语句和 WHEN 语句等。 |
|  系统信息函数  | 用于获取 MySQL 数据库的系统信息。其中包括获取数据库名的函数、获取当前用户的函数和获取数据库版本的函数等。 |
|    加密函数    | 用于对字符串进行加密解密。其中包括字符串加密函数和字符串解密函数等。 |
|    其他函数    | 包括格式化函数和锁函数等。                                   |

MySQL 的内置函数不但可以在 SELECT 查询语句中应用，同样也可以在 INSERT、UPDATE 和 DELETE 等语句中应用。例如，在 INSERT 语句中，应用日期时间函数获取紫铜的当前时间，并且将其添加到数据库中。MySQL 内置函数可以对表中数据进行相应的处理，以便得到用户希望得到的数据。



## 数学函数

数学函数是 MySQL 中最常用的一类函数，主要用于处理数字，包括整型和浮点数等。MySQL 中内置的数学函数及其作用如表。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\数学函数1.png)

![数学函数2](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\数学函数2.png)

![数学函数3](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\数学函数3.png)

![数学函数4](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\数学函数4.png)

![数学函数5](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\数学函数5.png)



### ABS(x)函数

ABS(x)函数用于求绝对值。使用 ABS(x)函数来求5和-5的绝对值，其语句如下。

```mysql
select ABS(5),ABS(-5);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ABS(x)函数.png)



### FLOOR(x)函数

FLOOR(x)函数返回小于或等于 x 的最大整数。应用 FLOOR(x)函数求小于或等于1.5及-2的最大整数，其语句如下。

```mysql
select FLOOR(1.5),FLOOR(-2);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\FLOOR(x)函数.png)



### RAND()函数

RAND()函数是返回0~1的随机数。运用 RAND()函数，获取两个随机数，其语句如下。

```mysql
select RAND(),RAND();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\RAND()函数.png)

生成3个1~100之间的随机数，使用ROUND(x)生成一个与 x 最接近的整数，当然，也可以使用 FLOOR(x)来生成一个小于或者等于 x 的最大整数。RAND()产生的是随机数，所以每次执行的结果都会是不一样的，其语句如下。

```mysql
select ROUND(RAND()*100),FLOOR(RAND()*100),CEILING(RAND()*100);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\RAND()乘一百函数.png)



### PI()函数

PI()函数用于返回圆周率。使用 PI()函数获取圆周率，其语句如下。

```mysql
select PI();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\PI()函数.png)



### TRUNCATE(x,y)函数

TRUNCATE(x,y)函数返回 x 保留到小数点后 y 位的值。使用 TRUNCATE(x,y)函数返回 2.1234567 小数点后3位的值，其语句如下。

```mysql
select TRUNCATE(2.1234567,3);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\TRUNCATE(x,y)函数.png)



### ROUND(x) 函数和 ROUND(x,y) 函数

ROUND(x)函数返回离 x 最近的整数，也就是对 x 进行四舍五入处理；ROUND(x,y)函数返回 x 保留到小数点后 y 位的值，截断时需要进行四舍五入处理。使用 ROUND(X)函数获取1.6和1.2最近的整数，使用 ROUND(x,y)函数获取1.123456小数点后3位的值，其语句如下。

```mysql
select ROUND(1.6),ROUND(1.2),ROUND(1.123456,3);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ROUND(x)和(x,y)函数.png)



### SQRT(x)函数

SQRT(x)函数用于求平方根。使用 SQRT(x)函数求16和25的平方根，其语句如下。

```mysql
select SQRT(16),SQRT(25);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SQRT(x)函数.png)



## 字符串函数

字符串函数是 MySQL 中最常用的一类函数，主要用于处理表中的字符串，其作用如表。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串函数1.png)

![字符串函数2](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串函数2.png)

![字符串函数3](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串函数3.png)

![字符串函数4](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串函数4.png)

![字符串函数5](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\字符串函数5.png)



### INSERT(s1,x,len,s2)函数

INSERT(s1,x,len,s2)函数将字符串 s1 中 x 位置开始长度为 len 的字符串用字符串 s2 替代。使用 INSERT 函数将 mrkj 字符串中的 kj 替换为 book，其语句如下。

```mysql
select INSERT('mrkj',3,2,'book');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\INSERT(s1,x,len,s2)函数.png)



### UPPER(s)函数和 UCASE(s)函数

UPPER(s)函数和UCASE(s)函数将字符串 s 的所有字母变成大写字母。下面使用 UPPER(s)函数和 UCASE(s)函数将 mrbccd 字符串中的所有字母变成大写字母，其语句如下。

```mysql
select UPPER('mrbccd'),UCASE('mrbccd');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\UPPER(s)函数和UCASE(s)函数.png)



### LEFT(s,n)函数

LFET(s,n)函数返回字符串 s 的前 n 个字符。应用 LEFT 函数返回 mrbccd 字符串的前两个字符，其语句如下。

```mysql
select LEFT('mrbccd',2);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\LEFT(s,n)函数.png)



### RTRIM(s)函数

RTRIM(s)函数将去掉字符串 s 结尾处的空格。应用 RTRIM 函数去掉 mr 结尾处的空格，其语句如下。

```mysql
select CONCAT('+',RTRIM('    mr    '),'+');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\RTRIM(s)函数.png)



### SUBSTRING(s,n,len)函数

SUBSTRING(s,n,len)函数从字符串 s 的第 n 个位置开始获取长度为 len 的字符串。下面使用 SUBSTRING 函数从 mrbccd 字符串的第三位开始获取4个字符，其语句如下。

```mysql
select SUBSTRING('mrbccd',3,4);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SUBSTRING(s,n,len)函数.png)



### REVERSE(s)函数

REVERSE(s)函数将字符串 s 的顺序反过来。下面使用 REVERSE(s)函数将 mrbccd 字符串的顺序反过来，其语句如下。

```mysql
select REVERSE('mrbccd');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\REVERSE(s)函数.png)



### FIELD(s,s1,s2,...)函数

FIELD(s,s1,s2,...)函数返回第一个与字符串 s 匹配的字符串的位置。应用 FIELD 函数返回第一个与字符串 mr 匹配的字符串的位置，其语句如下。

```mysql
select FIELD('mr','mrsoft','mrkj','mrbccd','mr');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\FIELD(s,s1,s2,...)函数.png)



### LOCATE(s1,s)函数、POSITION(s1 IN s)函数和 INSTR(s,s1)函数

在 MySQL 中，可以通过 LOCATE(s1,s)、POSITION(s1 IN s)函数和 INSTR(s,s1)函数获取子字符串相匹配的开始位置。这3个函数的语法格式如下。

（1）LOCATE(s1,s)：表示子字符串 s1 和在字符串 s 中的开始位置。

（2）POSITION(s1 IN s)：表示子字符串 s1 在字符串 s 中的开始位置。

（3）INSTR(s,s1)：表示子字符串 s1 在字符串 s 中的开始位置。

返回字符串“me”在字符串 'You love me.He love me' 中第一次出现的位置。其语句如下。

```mysql
select LOCATE('me','You love me.He love me');
select POSITION('me' IN 'You love me.He love me');
select INSTR('You love me.He love me','me');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\LOCATE(s1,s)函数POSITION(s1 IN s)函数和INSTR(s,s1)函数.png)



## 日期和时间函数

日期和时间函数是 MySQL 中另一最常用的函数，主要用于对表中的日期和时间数据的处理。MySQL 内置的日期时间函数及作用如表。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数1.png)

![日期函数2](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数2.png)

![日期函数3](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数3.png)

![日期函数4](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数4.png)

![日期函数5](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数5.png)

![日期函数6](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数6.png)

![日期函数7](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数7.png)

![日期函数8](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\日期函数8.png)



### CURDATE()函数和 CURRENT_DATE()函数

CURDATE()函数和 CURRENT_DATE()函数用于获取当前日期。下面使用 CURDATE()函数和CURRENT_DATE()函数获取当前日期，其语句如下。

```mysql
select CURDATE(),CURRENT_DATE();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CURDATE()函数和CURRENT_DATE()函数.png)



### CURTIME()函数和CURRENT_TIME()函数

CURTIME()函数和CURRENT_TIME()函数用于获取当前时间。下面使用 CURTIME()函数和CURRENT_TIME()函数获取当前时间，其语句如下。

```mysql
select CURTIME(),CURRENT_TIME();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CURTIME()函数和CURRENT_TIME()函数.png)



### NOW()函数

NOW()函数获取当前日期和时间。还有 URRENT_TIMESTAMP()函数、LOCALTIME()函数、SYSDATE()函数和 LOCALTIMESTAMP()函数也同样可以获取当前日期和时间。下面使用 NOW()函数、CURRENT_TIMESTAMP()函数、LOCALTIME()函数、SYSDATE()函数和 LOCALTIMESTAMP()函数来获取当前日期和时间，其语句如下。

```mysql
select NOW(),CURRENT_TIMESTAMP(),LOCALTIME(),SYSDATE();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\NOW()函数.png)



### DATEDIFF(d1,d2)函数

DATEDIFF(d1,d2)函数用于计算日期 d1 和 d2 之间相隔的天数。使用 DATEDIFF(d1,d2)函数计算 2011-07-05 与 2011-07-01 之间相隔的天数。其语句如下。

```mysql
select DATEDIFF('2011-07-05','2011-07-01');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\DATEDIFF(d1,d2)函数.png)



### ADDDATE(d,n)函数

ADDDATE(d,n)函数用于返回起始日期 d 加上 n 天数的日期。使用 ADDDATE(d,n)函数返回 2011-07-01 加上3天的日期，其语句如下。

```mysql
select ADDDATE('2011-07-01',3);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ADDDATE(d,n)函数.png)



### ADDDATE(a,INTERVAL expr type)函数

ADDDATE(a,INTERVAL expr type)函数返回起始日期 d 加上一个时间段后的日期。使用 ADDDATE(a,INTERVAL expr type)函数返回            2011-07-01 加上一年两个月后的日期，其语句如下。

```mysql
select ADDDATE('2011-07-01',INTERVAL '14' YEAR_MONTH);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ADDDATE(a,INTERVAL expr type)函数.png)



### SUBDATE(d,n)函数

SUBDATE(d,n)函数返回起始日期 d 减去 n 天的日期。使用 SUBDATE(d,n)函数返回 2011-07-01 减去6天后的日期，其语句如下。

```mysql
select SUBDATE('2011-07-01',6);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SUBDATE(d,n)函数.png)



## 条件判断函数

条件判断函数用来在 SQL 语句进行条件判断。根据不同的条件，执行不同的 SQL语句。MySQL 支持的条件判断函数及作用如表。

| 函数                                                         | 作用                                                         |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| IF(expr,v1,v2)                                               | 如果表达式 expr 成立，则执行 v1；否则执行 v2                 |
| IFNULL(v1,v2)                                                | 如果 v1 不为空，则显示 v1的值；否则显示 v2 的值              |
| CASE WHEN expr1 THEN v1 [WHEN expr2 THEN v2 ...] [ELSE vn] END | CASE 表示函数开始，END 表示函数结束。如果表达式 expr1 成立，则返回 v1 的值；如果表达式 expr2 成立，则返回 v2 的值。以此类推，最后遇到 else 时，返回 vn 的值。它的功能与PHP中的switch 语句类似。 |
| CASE expr WHEN e1 THEN v1 [WHEN e2 THEN v2 ...] [ELSE vn] END | CASE 表示函数开始，END 表示函数结束。如果表达式 expr 取值为 e1，则返回 v1 的值；如果表达式 expr 取值为 e2，则返回 v2 的值。以此类推，最后遇到 else 时，返回 vn 的值。 |

查询 tb_user 表中 字段 password 大于 555 的输出 “Very Good”；如果小于等于555大于222的，则输出 “Popularity”；否则输出 “Not Good”。其语句如下。

```mysql
select id,username,password, CASE WHEN password>555 THEN "Very Good" WHEN password<=555 AND password>222 THEN "Popularly" ELSE "Not Good" END level from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\条件判断函数.png)



## 系统信息函数

系统信息函数用来查询 MySQL 数据库的系统信息。例如，查询数据的版本，查询数据库的当前用户等。如表所示。

| 函数                                | 作用                             | 示例                                         |
| ----------------------------------- | :------------------------------- | :------------------------------------------- |
| VERSION()                           | 获取数据库的版本号               | select VERSION()；                           |
| CONNECTION_ID()                     | 获取服务器的连接数               | selec CONNECTION_ID()；                      |
| DATABASE(),SCHEMA()                 | 获取当前数据库名                 | select DATABASE(),SCHEMA()；                 |
| USER(),SYSTEM_USER(),SESSION_USER() | 获取当前用户                     | select USER(),SYSTEM_USER(),SESSION_USER()； |
| CURRENT_USER(),CURRENT_USER         | 获取当前用户                     | select CURRENT_USER()；                      |
| CHARSET(str)                        | 获取字符串 str 的字符集          | select CHARSET(’mrsoft)；                    |
| COLLATION(str)                      | 获取字符串 str 的字符排列方式    | select COLLATION('mrsoft')；                 |
| LAST_INSERT_ID()                    | 获取最近生成的 AUTO_INCREMENT 值 | select LAST_INSERT_ID()；                    |



### 获取 MySQL 版本号、连接数和数据库名的函数

VERSION()函数返回数据库的版本号；CONNECTION_ID()函数返回服务器的连接数，也就是到现在为止 MySQL 服务的连接的次数；DATABASE()函数和 SHCHEMA()函数返回当前数据库名。下面演示，其语句如下。

```mysql
select VERSION(),CONNECTION_ID(),DATABASE(),SCHEMA();
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\获取MySQL版本号连接数和数据库名的函数.png)



### 获取用户名的函数

USER()、SYSTEM_USER()、SESSION_USER()、CURRENT_USER()和 CURRENT_USER 这几个函数可以返回当前用户的名称。

```mysql
select USER(),SYSTEM_USER(),SESSION_USER(),CURRENT_USER()和,CURRENT_USER;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\USER()和SYSTEM_USER()和SESSION_USER(和,CURRENT_USER()和,CURRENT_USER;.png)



### 获取字符串的字符集和排序方式的函数

CHARSET(str)函数返回字符串 str 的字符集，一般情况下这个字符集就是系统的默认字符集；COLLATION(str)函数返回字符串 str 的字符排列方式。其语句如下。

```mysql
select CHARSET('aa'),COLLATION('aa');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\获取字符串的字符集和排列方式的函数.png)



## 加密函数

加密函数是 MySQL 中用来对数据进行加密的函数。因为数据库中有些很敏感的信息不希望被其他人看到，所以就可以通过加密的方式来使这些数据变成看似乱码的数据。例如，用户密码就应该进行加密。各种加密函数的作用如表所示。

<img src="C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\加密函数.jpg" style="zoom: 50%;" />



### 加密函数 PASSWORD(str)

PASSWORD(str)函数可以对字符串 str 进行加密。一般情况下，PASSQORD(str)函数主要是用来给用户的密码加密的。使用 PASSWORD(str)函数为字符串’abcd'加密，其语句如下。

```mysql
select  PASSWORD("adbc");
```



### 加密函数 MD5(str)

MD5(str)函数对字符串 str 进行加密。MD5(str)函数主要对普通的数据进行加密。使用 MD5(str)函数为字符串‘abcd’加密，其语句如下。

```mysql
select MD5('abcd');
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\MD5(str)函数.png)



## 其他函数

MySQL 中除了上述内置函数以外，还包括很多函数。例如，数字格式化函数 FORMAT(x,n)等如表所示。

<img src="C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\其他函数.jpg" style="zoom: 50%;" />



### 格式化函数 FORMAT(x,n)

FORMAT(x,n)函数可以将数字 x 进行格式化，将 x 保留到小数点后 n 位。这个过程需要进行四舍五入。例如，FORMAT(2.356,2)返回的结果将会是 2.36；FORMAT(2.353,2)返回的结果将会是2.35。使用 FORMAT(x,n)函数来将 235.3456 和 235.3454 进行格式化，都保留到小数点后3位，其语句如下。

```mysql
select FORMAT(235.3456,3),FORMAT(235.3454,3);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\FORMAT(x,n)函数.png)



### 改变字符集的函数

CONVERT(s USING cs)函数将字符串 s 的字符集变成 cs。将字符串 'ABC' 的字符集变成 gbk，其语句如下。

```mysql
select CHARSET('ABC'),CHARSET(CONVERT('ABC' USING gbk));
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\改变字符集的函数.png)



### 改变字段数据类型的函数

CAST(x AS type)和CONVERT(x type)这两个函数将 x 变成 type 类型。这两个函数只对 BINARY、CHAR、DATETIME、TIME、SIGNED INTEGER、UNSIGNED INTEGER 这些类型起作用。但这两种方法只是改变了输出值的数据类型，并没有改变表中字段的类型。下面  tb_user 表中的 createtime 字段为 DATETIME 类型，将其变为 DATE 类型或者 TIME 类型，其语句如下。

```mysql
select createtime,CAST(createtime as DATE),CONVERT(createtime,TIME) from tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\改变字段数据类型的函数.png)



# 第十一章       索引

在 MySQL 中，索引由数据表中一列或多列组合而成，创建索引的目的是为了优化数据库的查询速度。其中，用户创建的索引指向数据库中具体数据所在位置。当用户通过索引查询数据库中的数据时，不需要遍历所有数据库中的所有数据，大幅度提高了查询效率。



### MySQL 索引概述

MySQL索引的建立对于MySQL的高效运行是很重要的，索引可以大大提高MySQL的检索速度。打个比方，如果合理的设计且使用索引的MySQL是一辆兰博基尼的话，那么没有设计和使用索引的MySQL就是一个人力三轮车。拿汉语字典的目录页（索引）打比方，我们可以按拼音、笔画、偏旁部首等排序的目录（索引）快速查找到需要的字。索引分单列索引和组合索引。单列索引，即一个索引只包含单个列，一个表可以有多个单列索引，但这不是组合索引。组合索引，即一个索引包含多个列。创建索引时，你需要确保该索引是应用在 SQL 查询语句的条件(一般作为 WHERE 子句的条件)。实际上，索引也是一张表，该表保存了主键与索引字段，并指向实体表的记录。上面都在说使用索引的好处，但过多的使用索引将会造成滥用。因此索引也会有它的缺点：虽然索引大大提高了查询速度，同时却会降低更新表的速度，如对表进行INSERT、UPDATE和DELETE。因为更新表时，MySQL不仅要保存数据，还要保存一下索引文件。建立索引会占用磁盘空间的索引文件。



### MySQL 索引分类

MySQL 的索引包括普通索引、唯一性索引、全文索引、单列索引、多列索引和空间索引等。

（1）普通索引：普通索引，即不应用任何限制条件的索引，该索引可以在任何数据类型中创建。字段本身的约束条件可以判断其值是否为空或唯一。创建该类行索引后，用户在查询时，便可以通过索引进行查询。在某数据表的某个字段中，建立普通索引后。用户需要查询数据时，只需根据该索引进行查询即可。

（2）唯一性索引：使用 UNIQUE 参数可以设置唯一索引。创建该索引时，索引的值必须唯一，通过唯一索引，用户可以快速定位某条记录，主键是一种特殊唯一索引。

（3）全文索引：使用 FULLTEXT 参数可以设置索引为全文索引。全文索引只能创建在 CHAR、VARCHAR 或者 TEXT 类型的字段上。查询数据量较大的字符串类型的字段时，使用全文索引可以提高查询速度。例如，查询带有文章回复内容的字段，可以应用全文索引方式，需要注意的是，在默认情况下，应用全文搜索大小写不敏感。如果索引的列使用二进制排序后，可以执行大小写敏感的全文索引。

（4）单列索引：顾名思义，单列索引即只对应一个字段的索引。其可以包括上述叙述的3种索引方式。应用该索引的条件只需要保证该索引值对应一个字段即可。

（5）多列索引：多列索引是表的多个字段上创建一个索引。该索引指向创建时对应的多个字段，用户可以通过这几个字段进行查询。要想应用该索引，用户必须使用这些字段中的第一个字段。

（6）空间索引：使用 SPATIAL 参数可以设置索引为空间索引。空间索引只能建立在空间数据类型上，这样可以提高系统获取空间数据的效率。MySQL 中只有 MyISAM 存储引擎支持空间检索，而且索引的字段不能为空值。



## 创建索引



### 在建立数据表时创建索引

在建立数据表时可以直接创建索引，这种方式比较直接，且方便。易用。在建立数据表时创建索引的基本语法结构如下。

```mysql
create table table_name(
属性名 数据类型[约束条件],
属性名 数据类型[约束条件]
...
属性名 数据类型
[UNIQUE | FULLTEXT |SPATIAL] INDEX KEY
[别名](属性名1 [(长度)][ASC | DESC])
);
```

其中，属性名后的属性值，其含义如下。

（1）UNIQUE：可选项，表明索引为唯一性索引。

（2）FULLTEXT：可选项，表明索引为全文索引。

（3）SPATIAL：可选项，表明索引为空间索引。

（4）INDEX 和 KEY　参数用于指定字段索引，用户在选择时，只需要选择其中的一种即可；另外别名为可选项，其作用是给创建的索引取新名称；别名的参数如下。

属性名１：指索引对应的字段名称，该字段必须被预先定义。

长度：可选项，指索引的长度，必须是字符串类型才可以使用。

ASC | DESC：可选项，ASC 表示升序排列，DESC 参数表示降序排列。

**普通索引创建**

创建普通索引，即不添加 UNIQUE、FULLTEXT 等任何参数。下面创建表名为 sorce 的数据表，并将该表的 id 字段上建立索引。

```mysql
create table score(
id int(11) auto_increment primary key not null,
name varchar(50) not null,
math int(5) not null,
English int(5) not null,
chinese int(5) not null,
index(id));
使用 SHOW CREATE TABLE 语句查看该表的结构
SHOW CREATE TABLE score;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建普通索引.png)



**创建唯一性索引**

创建唯一性索引与创建一般索引的语法结构大体相同，但是在创建唯一性索引的时候，需要使用 UNIQUE 参数进行约束。创建一个表名为 address 的数据表，并指定该表的 id 字段上建立唯一索引，其代码如下。

```mysql
create table address(
id int(11) auto_increment primary key not null,
name varchar(50),
address varchar(200),
UNIQUE INDEX address(id ASC));
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建唯一性索引.png)



**创建全文索引**

与创建普通索引和唯一索引不同，全文索引的创建只能作用在 CHAR、VARCHAR、TEXT 类型的字段上。创建全文索引需要使用 FULLTEXT 参数进行约束。创建一个名称为 cards 的数据表，并在该表的 number 字段上创建全文索引，其代码如下。

```mysql
create table cards(
id int(11) auto_increment primary key not null,
name varchar(50),
number bigint(11),
info varchar(50),
FULLTEXT KEY cards_info(info)) engine=MyISAM;
```

说明：只有 MyISAM 类型的数据表支持 FULLTEXT 全文索引，InnoDB 或其他类型的数据表不支持全文索引。当用户在建立全文索引的时候，返回 “ERROR 1283(HY000):COolumn 'number' cannot be part of FULLTEXT index” 的错误，则说明用户操作的当前数据表不支持全文索引，即不为 MyISAM类型的数据表。



**创建单列索引**

创建单列索引，即在数据表的单个字段上创建索引。创建该类行索引不需要引入约束参数，用户在建立时只需要指定单列字段名，即可创建单列索引。创建名称为 telephone 的数据表，并制定在 tel 字段上建立名称为 tel_num 的单列索引，其代码如下。

```mysql
create table telephone(
id int(11) primary key auto_increment not null,
name varchar(50) not null,
tel varchar(50) not null,
index tel_num(tel(20)));
```

说明：数据表中的字段长度为50，而创建的索引的字段长度为20，这样做的目的是为了提高查询效率，优化查询速度。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建单列索引.png)



**创建多列索引**

与创建单列索引相仿，创建多列索引即指定表的多和字段即可实现。创建名称为 information 的数据表，并指定 name 和 sex 为多列索引，其代码如下。

```mysql
create table information(
id int(11) primary key auto_increment not null,
name varchar(50) not null,
sex varchar(50) not null,
birthday varchar(50) not null,
INDEX info(name,sex));
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建多列索引.png)



**创建空间索引**

创建空间索引时，需要设置 SPATIAL 参数。同样，必须说明的是，只有 MyISAM 类型表支持该类型索引。而且，索引字段必须有非空约束。创建一个名称为 list 的数据表，并创建一个名为 listinfo 的空间索引，其代码如下。

```mysql
create table list(
id int(11) primary key auto_increment not null,
goods geometry not null,
SPATIAL INDEX listinfo(goods)
)engine=MyISAM;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建空间索引.png)



### 在已建立的数据表中创建索引

在 MySQL 中，不但可以在用户创建数据表时创建索引，用户也可以直接在已经创建的表中，在已经存在的一个或几个字段上创建索引。其基本的命令结构如下所示。

```mysql
CREATE [UNIQUE | FULLTEXT |SPATIAL ] INDEX index_name
ON table_name(属性 [(ength)][ASC | DESC]);
```

命令的参数说明如下。

（1）index_name 为索引名称，该参数作用是给用户创建的索引赋予新的名称。

（2）table_name 为表名，即指定创建索引的表名称。

（3）可选参数，指定索引类型，包括 UNIQUE（唯一索引）、FULLTEXT（全文索引）、SPATIAL（空间索引）。

（4）属性参数，指定索引对应的字段名称。该字段必须已经预存在用户想要操作的数据表中，如果该数据表中不存在用户指定的字段，则系统会提示异常。

（5）length 为可选参数，用于指定索引长度。

（6）ASC 和 DESC 参数，指定数据表的排序顺序。

```mysql
创建普通索引：create INDEX user_info ON tb_user(id);//create INDEX 索引名 ON 数据表名称（字段名称）;

创建唯一索引：create UNIQUE INDEX user_info ON tb_user(id);//create UNIQUE INDEX 索引名 ON 数据表名称（字段名称）;

创建全文索引：create FULLTEXT INDEX user_name ON tb_user(username);
//create FULLTEXT INDEX 索引名 ON 数据表名称（字段名称）;

创建单列索引：create INDEX user_info ON tb_user(username(20));
//create INDEX 索引名 ON 数据表名称（字段名称（字段长度））;

创建多列索引：create INDEX user_info ON tb_user(username,password);
//create INDEX 索引名 ON 数据表名称（字段名称1,字段名称2,...）;

创建空间索引：create SPATIAL INDEX 索引名 ON 数据表名称（字段名称）;
```



### 修改数据表结构添加索引

修改已经存在表上的索引，可以通过 ALTER TABLE 语句为数据表添加索引，其基本结构如下。

```mysql
ALTER TABLE table_name ADD [UNIQUE | FULLTEXT | SPATIAL] INDEX index_name(属性名 [(length)] [ASC | DESC]);

添加普通索引：alter table tb_user ADD INDEX user_info(id(11));
添加唯一索引：alter table tb_user ADD UNIQUE INDEX user_info(id(11));
添加全文索引：alter table tb_user ADD FULLTEXT INDEX user_info(id(11));
添加单列索引：alter table 数据表名称 ADD INDEX 索引名(字段名称（字段长度）);
添加多列索引：alter table 数据表名称 ADD INDEX 索引名(字段名称1,字段名称2,...);
添加空间索引：alter table 数据表名称 ADD SPATIAL INDEX 索引名(字段名称);
```



## 删除索引

在 MySQL 中，创建索引后，如果用户不再需要该索引，则可以删除指定表的索引。因为这些已经被建立且不常使用的索引，一方面可能会占用系统资源，另一方面也可能导致更新速度下降，这集大地影响了数据表的性能。所以，在用户不需要该表的索引时，可以手动删除指定索引。其中，删除索引可以通过 DROP 语句来实现。其基本的命令如下。

```mysql
DROP INDEX index_name ON table_name;
```





# 第十二章       视图



## 视图概述

视图是由数据库中的一个表或多个表导出的虚拟表，方便用户对数据的操作。

### 视图的概念

视图（view）是一种虚拟存在的表，是一个逻辑表，本身并不包含数据。作为一个select语句保存在数据字典中的。
通过视图，可以展现基表(用来创建视图的表)的部分数据；视图数据来自定义视图的查询中使用的表，使用视图动态生成。
为什么要使用视图？因为视图的诸多优点，如下：
（1）简单：使用视图的用户完全不需要关心后面对应的表的结构、关联条件和筛选条件，对用户来说已经是过滤好的复合条件的结果集。
（2）安全：使用视图的用户只能访问他们被允许查询的结果集，对表的权限管理并不能限制到某个行某个列，但是通过视图就可以简单的实现。
（3）数据独立：一旦视图的结构确定了，可以屏蔽表结构变化对用户的影响，源表增加列对视图没有影响；源表修改列名，则可以通过修改视图来解决，不会造成对访问者的影响。

1.如果应用建立在数据库表上，当数据库表发生变化时，可以在表上建立视图，通过视图屏蔽表的变化，从而使应用程序可以不动。

2.如果应用建立在数据库表上，当应用发生变化时，可以在表上建立视图，通过视图屏蔽应用的变化，从而使数据库表不动。

3.如果应用建立在视图上，当数据库表发生变化时，可以在表上修改视图，通过视图屏蔽表的变化，从而使应用程序可以不动。

4.如果应用建立在视图上，当应用发生变化时，可以在表上修改视图，通过视图屏蔽应用的变化，从而使数据库可以不动。

总而言之，使用视图的大部分情况是为了保障数据安全性，提高查询效率。



## 创建视图

创建视图是指在已经存在的数据库表上建立视图，视图可以建立在一张表中，也可以建立在多个表中。

### 查看创建视图的权限

创建视图需要具有 CREATE VIEW 的权限，同时应该具有查询涉及的列的 SELECT 权限。可以使用 SELECT 语句来查询这些权限信息，查询语法如下。

```mysql
SELECT Select_priv,Create_view_priv FROM mysql.user WHERE user='用户名';
```

（1）Selete_priv 属性表示用户是否具有 SELECT 权限，Y 表示拥有 SELECT 权限，N 表示没有。

（2）Create_view_priv 属性表示用户是否具有 CREATE VIEW 权限；mysql.user 表示 MySQL 数据库下面的 user 表。

（3）“用户名” 参数表示要查询是否拥有 DROP 权限的用户，该参数需要用单引号引起来。

下面查询 MySQL 中 root 用户是否具有创建视图的权限，代码如下。

```mysql
SELECT Select_priv,Create_view_priv FROM mysql.user WHERE user='root';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查看创建视图的权限.png)

结果中 Select_priv 和 Create_view_priv 属性的值都为 Y，这表示 root 用户具有 SELECT 和 CREATE VIEW 权限。



### 创建视图的步骤

MySQL 中，创建视图是通过 CREATE VIEW 语句实现的，其语法如下。

```mysql
CREATE [ALGORITHM={UNDEFINED | MERGE | TEMPTABLE}]
       VIEW 视图名[(属性清单)]
       AS SELECT 语句
       [WITH [CASCADED | LOCAL] CHECK OPTION];
```

（1）ALGORITHM 是可选参数，表示视图选择的算法；

（2）“视图名” 参数表示要创建的视图名称；

（3）“属性清单” 是可选参数，指定视图中各个属性的名词，默认情况下与 SELECT 语句中查询的属性相同；

（4）SELECT 语句参数是一个完整的查询语句，表示从某个表中查出某些满足条件的记录，将这些记录到入视图中；

（5）WITH CHECK OPTION 是可选参数，表示更新视图时要保证在该视图的权限范围之内。

在数据表 tb_user 中创建 view1 视图，视图命名为 user_view1，并设置视图属性分别为 a_id、a_name、a_pwd，代码如下。

```mysql
CREATE VIEW
user_view(a_id,a_name,a_pwd)
AS SELECT id,username,password
FROM tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\创建视图.png)

如果要在 tb_book 表和 tb_user 表上创建名为 book_view1 的视图，执行代码如下 。

```mysql
CREATE ALGORITHM=MERGE VIEW
user_view(a_sort,a_name,a_talk,a_books)
AS SELECT sort,talk,books,tb_user.name
FROM tb_user,tb_book; WHERE tb_user.id=tb.book.id
WITH LOCAL CHECK OPTION;
```



### 创建视图的注意事项

(1) 运行创建视图的语句需要用户具有创建视图(CRATE VIEW)的权限，若加了[OR REPLACE]时，还需要用户具有删除视图(DROP VIEW)的权限；

(2) SELECT语句不能包含FROM子句中的子查询；

(3) SELECT语句不能引用系统或用户变量；

(4) SELECT语句不能引用预处理语句参数；

(5) 在存储子程序内，定义不能引用子程序参数或局部变量；

(6) 在定义中引用的表或视图必须存在。但是，创建了视图后，能够舍弃定义引用的表或视图。要想检查视图定义是否存在这类问题，可使用CHECK TABLE语句；

(7) 在定义中不能引用TEMPORARY表，不能创建TEMPORARY视图；

(8) 在视图定义中命名的表必须已存在；

(9) 不能将触发程序与视图关联在一起；

(10) 在视图定义中允许使用ORDER BY，但是，如果从特定视图进行了选择，而该视图使用了具有自己ORDER BY的语句，它将被忽略。



## 视图操作



### 查看视图

查看视图是指查看数据库中已存在的视图。查看视图必须要有 SHOW VIEW 的权限。查看视图的方法主要包括 DESCRIBE 语句、SHOW TABLE STATUS 语句、SHOW CREATE VIEW 语句等。

**DESCRIBE 语句**

DESCRIBE 可以缩写成 DESC，其语法格式如下。

```mysql
DESCRIBE 视图名;
```

下面使用 DESC 语句查询 user_view 视图中的结构。

```mysql
DESC user_view;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\查看视图.png)

**SHOW TABLE STATUS 语句**

在 MySQL中，可以使用 SHOW TABLE STATUS 语句查看视图的信息，其语法格式如下。

```mysql
SHOW TABLE STATUS LIKE '视图名';
```

（1）“ LIKE ” 表示后面匹配的是字符串；

（2）“ 视图名 ” 参数指要查看的视图名称，需要用单引号定义。

下面使用 SHOW TABLE STATUS 语句查看视图 user_view 中的信息，代码如下。

```mysql
SHOW TABLE STATUS LIKE 'user_view';
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SHOW_TABLE_STATUS.png)

从执行结果可以看出，存储引擎、数据长度等信息都显示为 NULL ，则说明视图为虚拟表，与普通数据表时有区别的，下面使用 SHOW TABLE STATUS 语句来查看 tb_user 表的信息，执行结果如图。

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SHOW_TABLE_STATUS数据表.png)

**SHOW CREATE VIEW 语句**

在 MySQL 中，SHOW CREATE VIEW 语句可以查看视图的详细定义，其语法格式如下。

```mysql
SHOW CREATE VIEW 视图名
```

下面使用 SHOW CREATE VIEW 语句查看视图 user_view 的信息，代码入下。

```mysql
SHOW CREATE VIEW user_view;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\SHOW_CREATE_VIEW语句.png)



### 修改视图

修改视图是指修改数据库中已存在的表的定义。当基本表的某些字段发生改变时，可以通过修改视图，视图来保持视图和基本表之间一致。MySQL 中通过 CREATE OR REPLACE VIEW 语句和 ALTER 语句来修改视图。下面介绍这两种修改视图的方法。

**CREATE OR REPLACE VIEW**

在 MySQL 中，CREATE OR REPLACE VIEW 语句可以使用修改视图。该语句的使用非常灵活。在视图已经存在的情况下，对视图进行修改；视图不存在时，可以创建视图。CREATE OR REPLACE VIEW 语句的语法如下。

```mysql
CREATE OR REPLACE [ALGORITHM={UNDEFINED | MERGE | TEMPTABLE }]
VIEW 视图[(属性清单)]
AS SELEcT 语句
[WITH [CASCADED |LOCAL] CHECK OPTION]
```

下面使用 CREATE OR REPLACE VIEW 语句将视图 user_view 的字段修改为 a_name 和 a_id.

```mysql
CREATE OR REPLACE ALGORITHM=TEMPTABLE
VIEW user_view(a_id,a_name)
AS SELECT id,username FROM tb_user;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\CREATE_OR_REPLACE_VIEW语句.png)

**ALTER**

ALTER VIEW 语句改变了视图的定义，包括被索引视图，但不影响所依赖的存储过程或触发器。该语句与 CREATE VIEW 语句有着同样的限制，如果删除并重建了一个视图，就必须重新为它分配权限。ALTER VIEW 语句的语法如下。

```mysql
alter view [algorithm={merge | temptable | undefined}]
view view_name [(column_list)]
as select_statement
[with [cascaded | local] check option]
```

（1）algorithm：该参数已经在创建视图中做了介绍，这里不再介绍。

（2）view_name：视图的名称。

（3)select_statement：SQL 语句用于限定视图。

**注意：**在创建视图时，在使用了 WITH CHECK OPTION，WITH ENCRYPTION，WITH SCHEMABING 或 VIEW_METADETA 选项时，如果想保留这些选项提供的功能，必须在 ALTER VIEW 语句中将它们包括进去。

下面将对 user_view 视图进行修改，将原有的 a_id 和 a_name ；两个属性更改为 a_id 一个属性。代码如下。

```mysql
ALTER VIEW user_view(a_id)
AS SELECT id FROM tb_user
WITH CHECK OPTION;
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MySQL_image\ALTER_VIEW语句.png)



### 更新视图

对视图的更新其实就是对表的更新，更新视图是指通过视图来插入 （INSERT）、更新（UPDATE）和删除（DELETE）表中的数据。因为视图是一个虚拟表，其中没有数据。通过视图更新时，都是转换到基本表来更新。更新视图时，只能更新权限范围内的数据，超出了范围，就不能更新。

**更新视图**

下面更新视图中的 id 为46的记录，a_name 的值为 May，a_pwd 的值为 999，代码如下。

```mysql
UPDATE user_view SET a_name='May',a_pwd='999' WHERE a_id=46;
```

**更新视图的限制**

并不是所有的视图都可以更新，以下几种情况是不能更新视图的。

（1）视图中包含 COUNT()、SUM()、MAX() 和 MIN() 等函数。例如：

```mysql
CREATE VIEW user_view(a_id,a_name)
AS SELECT id,username,COUNT(password) FROM tb_user;
```

（2）视图中包含 UNION、UNION ALL 、DISTINCT、GROUP BY 和 HAVIG 等关键字。例如：

```mysql
CREATE VIEW user_view(a_id,a_name)
AS SELECT id,username FROM tb_user GROUP BY id;
```

（3）常量视图。例如：

```mysql
CREATE VIEW user_view
AS SELECT 'Aric' as a_name;
```

（4）视图中的 SELECT 中包括子查询。例如：

```mysql
CREATE VIEW user_view(a_id)
AS SELECT (SELECT id FROM tb_user);
```

（5）由不可更新的视图导出的视图。例如：

```mysql
CREATE VIEW user_view
AS SELECT * FROM user_view;
```

（6）创建视图时，ALGORITHM 为 TEMPTABLE 类型。例如：

```mysql
CREATE ALGORITHM=TEMPTABLE
VIEW user_view
AS SELECT * FROM tb_user;
```

（7）视图对应的表上存在没有默认值的列，而且该列没有包含在视图里。例如，表中包含的 username 字段没有默认值，但是视图中不包括该字段，那么这个视图是不能更新的。因为，在更新视图时，这个没有默认值的记录将没有值插入，也没有 NULL 值插入。数据库系统是不会允许这样的情况出现的，其会阻止这个视图更新。



### 删除视图

删除视图是指删除数据库中已存在的视图。删除视图时，只能删除视图的定义，不会删除数据。MySQL 中，使用 DROP VIEW 语句来删除视图。但是，用户必须拥有 DROP 权限。

DROP VIEW 语句的语法如下。

```mysql
DROP VIEW EXISTS <视图名> [RESTRICT | CASCADE]
```





# 第十三章       数据完整性约束



## 定义完整性约束



### 实体完整性

实体（Entity）是一个数据对象，是指客观存在并可以相互区分的事物，如一个教师、一个学生或一个雇员等。一个实体在数据库中表现为表中的一条记录。通常情况下，它必须遵守实体完整性规则。在 MySQL 中，实体完整性是通过主键约束和候选键约束来实现的。

**1、主键约束**

主键可以是表中的某一列，也可以是表中多个列所构成的一个组合；其中，有多个列组合而成的主键也成为复合主键。在 MySQL 中，主键列必须遵守以下规则。

（1）每一个表只能定义一个主键。

（2）唯一性原则。主键的值，也称键值，必须能够唯一标识表中的每一行记录，且不能为 NULL。也就是说一张表中两个不同的行在主键上不能具有相同的值。

（3）最小化规则。复合主键不能包含不必要的多余列。也就是说，当从一个复合主键中删除一列后，如果剩下的列构成的主键仍然满足唯一性原则，那么这个复合主键是不正确的。

（4）一个列名在复合主键的列表中只能出现一次。



**1）作为列的完整性约束**

在 MySQL 中，可以在 CREATE TABLE 或者 ALTER TABLE 语句中，使用 PRIMARY KEY 子句来创建主键约束，其实现方式有以下两种。在创建用户信息表 tb_admin 时，将 id 字段设置为主键，代码如下。

```mysql
create table tb_admin(
    id int auto_increment primary key,
    user varchar(30) not null,
    password varchar(30) not null,
    createtime datetime
);
```

**2）作为表的完整性约束**

在表的所有列的属性定义后，加上 PRIMARY KEY(index_col_name,...)子句实现。创建学生信息表 tb_student 时，将学号（id）和所在班级号（classid）字段设置为主键，代码如下。

```mysql
create table tb_student(
    id int auto_increment,
    name varchar(30) not null,
    sex varchar(2),
    classid int not null,
    birthday date,
    PRIMARY KEY(id,classid)
);
```



**2、候选键约束**

如果一个属性集能唯一标识元组，且有不含有多余的属性，那么这个属性集成为关系的候选键。候选键可以是表中的某一列，候选键可以在 CREATE TABLE 或者 ALTER TABLE 语句中使用关键字 UNIQUE 来定义，其实现方法与主键约束类似，也是可作为列的完整性约束或者表的完整性约束两种方式。在 MySQL 中，候选键与主键之间存在以下两点区别。

（1）一个表中只能创建一个主键，但可以定义若干个候选键。

（2）定义主键约束时，系统会自动创建 PRAMARY KEY 索引，而定义候选键约束时，系统会自动创建 UNIQUE 索引

在创建用户信息表 tb_user1 时，将 id 字段和 user 字段设置为候选键，代码如下。

```mysql
create table tb_user1(
id int auto_increment UNIQUE,
user varchar(30) not null,
password varchar(30) not null,
createtime TIMESTAMP default CURRENT_TIMESTAMP);
```



### 参照完整性

参照完整性是关系模型的完整约束之一，属于数据完整性的一种，其余还有：实体完整性、用户自定义完整性。

[参照完整性规则]：若属性或属性组F是基本关系R的[外键]，它与基本关系S的主键Ks相对应（基本关系R和S不一定是不同的关系），则对于R中的每个元组在F上的值必须为：

（1）空值，F的每个属性值均为空值。

（2）S中某个元组中的主键值（主码值）。

即参照的关系中的属性值必须能够在被参照关系找到或者取空值，否则不符合数据库的[语义]。在实际操作时如更新、删除、插入一个表中的数据，通过参照引用相互关联的另一个表中的数据，来检查对表的数据操作是否正确，不正确则拒绝操作。

#### 同一关系

[![img](https://bkimg.cdn.bcebos.com/pic/ac4bd11373f08202386b21c943fbfbedaa641b4e?x-bce-process=image/resize,m_lfit,w_366,limit_1/format,f_auto)](https://baike.baidu.com/pic/参照完整性/1230891/0/ac4bd11373f08202386b21c943fbfbedaa641b4e?fr=lemma&ct=single)

在参照完整性规则中，R和S可以是同一个关系。

在学生（学号，姓名，性别，年龄，专业号，班长）关系中，“学号”属性是主键，“班长”属性表示该学生所在班级的班长的学号，因此它应用的本关系“学号”属性。按照参照完整性规则，“班长”属性可以取以下两类值：

（1）空值，表示该学生所在班级尚未选出班长。

（2）非空值，该值必须是本关系中某个元组的学号值，即某个当选班长的学生的学号值。 [2] 

#### 两个关系间

如学生[实体]和专业实体可以用下列[关系模式]来表示，其中学号是学生的[主键]，专业号是专业的主键：

学生（学号，姓名，性别，专业号，年龄）

专业（专业号，专业名）

这两个关系之间存在着属性的引用（含有相同的[属性]“专业号”），学生关系引用了专业关系的主键“专业号”，专业号则是学生关系的外键。而且按照参照完整性规则，学生关系（并非专业关系）中的每个[元组]的“专业号”属性只能取两种值：

（1）[空值]，表示尚未给学生分配专业。

（2）非空值，这时该值必须是专业关系中某个元组的“专业号”值，表示该学生不可能分配到一个不存在的专业中去。就是说学生关系中的某个属性的取值需要参照专业关系的属性取值。

#### 两个以上的关系

两个以上的[关系]也可以存在引用关系，学生、课程、选课（学生与课程）之间的联系可以用下列三个关系来表示：

学生（学号，姓名，性别，专业号，年龄）

专业（专业号，专业名）

选课（学号，课程号，成绩）

这里的“学号”和“课程号”属性都是选课关系的外键，但只有“学号”和“课程号”联合起来才能确定选课的关系，所以这里存在一个复合主键关系，（学号，课程号）是选课关系的主键。虽然按照参照完整性可以取两类值，但是由于[实体完整性]，复合主键中的每个属性均不能取空值。所以选课关系中的”学号“和”课程号”属性实际上只能取被参照关系（学生关系和专业关系）中已经存在的主键值。即选课关系中的“学号”值必须是确实存在的学生的学号，学生关系中有该学生的记录；选课关系中的“课程号”值也必须是确定存在的课程的课程号，即课程关系中有该课程的记录。

#### 性质

参照完整性属于表间规则。对于永久关系的相关表，在更新、插入或删除记录时，如果只改其一不改其二，就会影响数据的完整性：例如修改父表中关键字值后，子表关键字值未做相应改变；删除父表的某记录后，子表的相应记录未删除，致使这些记录成为孤立记录；对于子表插入的记录，父表中没有相应关键字值的记录；等等。对于这些涉及表间数据的完整性，统称为参照完整性。

参照完整性则是相关联的两个表之间的约束，具体的说，就是从表中每条记录外键的值必须是主表中存在的,因此，如果在两个表之间建立了关联关系，则对一个关系进行的操作要影响到另一个表中的记录。

如果实施了参照完整性，那么当主表中没有相关记录时，就不能将记录添加到相关表中。也不能在相关表中存在匹配的记录时删除主表中的记录，更不能在相关表中有相关记录时，更改主表中的主键值。也就是说，实施了参照完整性后，对表中主键字段进行操作时系统会自动地检查主键字段，看看该字段是否被添加、修改、删除了。如果对主键的修改违背了参照完整性的要求，那么系统就会自动强制执行参照完整性。



MySQL 有两种常用的引擎类型（MyISAM 和 InnDB），目前 InnDB 引擎类型支持外键约束。InnDB 引擎类型中声明外键的基本语法格式如下。

```mysql
[CONSTRAINT[SYMBOL]]
FOREIGN KEY (index_col_name,...) reference_definition
```

reference_definition 主要用于定义外键所参照的表、列、参照动作的声明和实施策略等4部分内容。

```mysql
REFERENCES tbl_name[(index_col_name,...)]
           [MATCH FULL | MATCH PARTIAL |MATCH |SIMPLE]
           [ON DEFAULT reference_option]
           [ON UPDATE reference_option]
```

index_col_name 的语法格式如下。

```mysql
col_name[(length)][ASC | DESC]
```

reference_option 的语法格式如下。

```mysql
RESTRICT | CASCADE | SET NULL |NO ACTION
```

参数说明如下。

（1）index_col_name：用于指定被设置为外键的列。

（2）tbl_name：用于指定外键所参照的表名。这个表称为参照表（或父表），而外键所在的表称作参照表（或子表）。

（3）col_name：用于指定被参照的列名。外键可以引用被参照表中的主键或候选键，也可以引用被参照表中某些列的一个组合，但这个组合不能是被参照表中随机的一组列，必须保存该组合的取值在被参照表中是唯一的。外键中所有列值在被参照表的列中必须全部存在，也就是通过外键来对参照表某些列（外键）的取值进行限定与约束。

（4）ON DEFAULT | ON UPDATE：指定参照动作相关的 SQL 语句。可为每个外键指定对应于 DEFAULT 语句和 UPDATE 语句的参照动作。

（5）reference_option：指定参照完整性约束的实现策略。其中，当没有明确指定参照完整性的实现策略时，两个参照动作会默认使用 RESTRICT。具体的策略可选值如表所示。

| 可选值    | 说明                                                         |
| --------- | ------------------------------------------------------------ |
| RESTRICT  | 限制策略：当要删除或更新被参照表中被参照列上，并在外键中出现的值时，系统拒绝对被参照表的删除或更新操作 |
| CASCADE   | 级联策略：从被参照表中删除或更新记录行时，自动删除或更新参照表匹配的记录行 |
| SET NULL  | 置空策略：当从被参照表中删除或更新记录行时，设置参照表中与之对应的外键列的值为 NULL。这个策略需要被参照表中的外键列没有声明限定词 NOT NULL |
| NO ACTION | 不采取实施策略：当一个相关的外键值在被参照表中时，删除或更新被参照表中键值的动作不被允许。该策略的动作语言与 RESTRICT 相同 |

创建学生信息表 tb_student1，并为其设置参照完整性约束（拒绝删除或更新被参照表中被参照列上的外键值），即将 classid 字段设置为外键，代码如下。

```mysql
create table tb_student1(
id int auto_increment,
name varchar(30) not null,
sex varchar(2),
classid int not null,
birthday date,
remark varchar(100),
primary key(id),
FOREIGN KEY(classid)
REFERENCES tb_class(id)
ON DELETE RESTRICT
ON UPDATE RESTRIct);
```

设置外键时，通常需要遵守以下规则。

（1）被参照表必须是已经存在的，或者是当前正在创建的表。如果是当前正在创建的表，也就是说，被参照表与参照表是同一个表，这样的表称为自参照表（Self-referencing Table），这种结构称为自参照完整性（Self-referential Integrity）。

（2）必须为被参照表定义主键。

（3）必须在参照表名后面指定列名或列名的组合。这个列或列组合必须是这个被参照表的主键或候选键。

（4）外键中列的数目必须和被参照表中的列的数据相同。

（5）外键中列的数据类型必须和被参照表的主键（或候选键）中的对应列的数据类型相同。

（6）尽管主键是不能够包含空值的，但允许在外键中出现一个空值。这意味着，只要外键的每个非空值出现在指定的主键中，这个外键的内容就是正确的。



### 用户定义完整性

用户定义完整性规则（User-defined Integrity Rule）是针对某一应用环境的完整性约束条件，它反映了某一具体应用所涉及的数据应满足的要求。关系模型提供定义和检验这类完整性规则的机制，其目的是由系统来统一处理，而不再由应用程序来完成这项工作。在实际系统中，这类完整性规则一般是在建立数据表的同时进行定义，应用编程人员不需要再做考虑，如果某些约束条件没有建立在库表一级，则应用编程人员应在各模块的具体编程中通过程序进行检查和控制。

MySQL 支持非空约束、CHECK 约束和触发器3种用户自定义完整性约束。

**1、非空约束**

在 MySQL 中，非空约束可以通过在 CREATE TABLE 或 ALTER TABLE语句中，某个列定义后面加上关键字 NOT NULL 来定义，用来约束该列的取值不能为空。创建班级信息表 tb_class1，并为其 name 字段添加非空约束，代码如下。

```mysql
CREATE TABLE tb_class1(
id int(11) NOT NULL AUTO_INCREMENT,
name varchar(45) NOT NULL,
remark varchar(100) DEFAULT NULL,
PRIMARY KEY('id'));
```

**2、CHECK 约束**

与非空约束一样，CHECK 约束也可以通过在 CREATE TABLE 或 ALTER TABLE 语句中，根据用户的实际完整性要求来定义。它可以分别对列或表实施 CHECK 约束，其中使用的语法如下。

```mysql
CHECK(expr)
```

其中，expr 是一个 SQL 表达式，用于指定需要检查的限定条件。在更新表数据时，MySQL 会检查更新后的数据行是否满足 CHECK 约束中的限定条件。该限定条件可以是简单的表达式，也可以是复杂的表达式（如子查询）。

1）对列实施 CHECK 约束

```mysql
create table tb_student2(
id int auto_increment,
name varchar(30) not null,
sex varchar(2),
age int not null CHECK(age>6 and age<18),
remark varchar(100),
primary key(id));
```

2）对表实施 CHECK 约束

```mysql
create table tb_student3(
id int auto_increment,
name varchar(30) not null,
sex varchar(2),
classid int not null,
birthday date,
remark varcahr(100),
primary key(id),
CHECK(classid IN (SELECT id FROM tb_class)));
```



## 命名完整性约束

在 MySQL 中，也可以对完整性约束进行添加、修改和删除等操作。其中，为了删除和修改完整性约束，需要在定义约束的同时对其进行命名。命名完整性约束的方式是在各种完整性约束的定义说明之前加上 CONSTRAINT 字句实现的，CONSTRAINT 子句的语法格式如下。

```mysql
CONSTRAINT<symbol>
      [PRIMARY KEY 短语 | FOREIGN KEY 短语 | CHECK 短语]
```

参数说明如下。

（1）symbol：用于指定约束名称。这个名字是在完整性约束说明的前面被定义，在数据库里必须是唯一的。如果在创建时没有指定约束的名字，则 MySQL 将自动创建一个约束名字。

（2）PRIMARY KEY 短语：主键约束。

（3）FOREIGN KEY 短语：外键约束。

（4）CHECK 短语：CHECK 约束。

例如，对雇员表添加主键约束，并为其命名为 PRIMARY，可以使用下面的代码。

```mysql
ALTER TABLE 雇员表 ADD CINSTRAINT PRIMARY
PRIMARY KEY(雇员编号)
```

重新创建学生信息表 tb_student1，命名为 tb_student1a，并为其参照完整性命名，代码如下。

```mysql
create table tb_student1a(
id int auto_increment PRIMARY KEY,
name varchar(30) not null,
sex varcahr(2),
classid int not null,
birthday date,
remark varchar(100),
CONSTRAINT fk_classid FOREIGN KEY(classid)
REFERENCES tb_classid(id)
ON DELETE RESTRICT
ON UPDATE RESTRICT);
```



## 更新完整性约束



### 删除完整性约束

在 MySQL 中，使用 ALTER TABLE 语句，可以独立地删除完整性约束，而不会删除表本身。如果使用 DROP TABLE 语句删除一个表，那么表中的所有完整性约束也会自动被删除。删除完整性约束需要在 ALTER TABLE 语句中使用 DROP 关键字来实现，具体的语法格式如下。

```mysql
DROP [FOREIGN KEY | INDEX | <symbol>] | [PRIMARY KEY]
例如：
ALTER TABLE tb_student1a DROP FOREIGN KEY fk_classid;
```



### 修改完整性约束

具体语法如下。

```mysql
ADD CONSTRAINT <symbol> 各种约束
例如：
ALTER TABLE tb_student1a
ADD CONSTRAINT fk_classid FOREIGN KEY（classid)
REFERENCES tb_class(id)
ON DELETE CASCADE
ON UPDATE CASCADE;
```





# 第十四章       存储过程与存储函数



## 创建存储过程和存储函数



### 创建存储过程

在 MySQL 中，创建存储过程的基本形式如下。

```mysql
CREATE PROCEDURE sp_name([proc_parameter[...]])
       [characteristic ...] routine_body
```

其中，sp_name 参数是存储过程的名称；proc_parameter 表示存储过程的参数列表；characteristic 参数指定存储过程的特性；routine_body 参数是 SQL 代码内容，可以使用 BEGIN...END 来标识 SQL 代码的开始和结束。

```mysql
delimiter//
create procedure proc_name(in parameter integer)
begin
declare variable varchar(20);
if parameter=1 then
set variable='MYSQL',
else
set variable='PHP';
end if;
insert into tb(name) values(variable);
end;
```

存储过程创建之后，可用如下语句进行删除，参数 proc_name 指存储过程名。

```mysql
drop procedure proc_name
```



### 创建存储函数

创建存储函数与存储过程大体相同，创建存储函数的基本语法如下。

```mysql
CREATE FUNCTION sp_name([func_parameter[,..]])
    RETURNS type
    [characteristic...] routine_body
```

其中，sp_name 参数是存储过程的名称；proc_parameter 表示存储过程的参数列表；characteristic 参数指定存储过程的特性；routine_body 参数是 SQL 代码内容，RETURN type 指定返回值的类型。例子如下。

```mysql
delimiter//
create function name_of_student(std_id INT)
returns varchar(50)
begin
return(select name from studentinfo where sid=sid_id);
end
//
```



### 变量的应用

MySQL 存储过程中参数主要有局部参数和会话参数两种，这两种参数又可以被称为局部变量和会话变量。局部变量只在定义该局部变量的 begin...end 范围内有效，会话变量在整个存储过程范围内均有效。

**1、局部变量**

局部变量以关键字 DECLARE 声明，后跟变量名和变量类型，例如：

```mysql
declare a int
```

当然，声明局部变量时也可以用关键字 DEFAULT 为变量指定默认值，例如：

```mysql
declare a int default 10
```

例子如下：

```mysql
delimiter//
create procedure p1()
begin
declare x char(10) default 'outer';
begin
declare x char(10) default 'inner';
select x;
end;
select x;
end;
//
```



**2、全局变量**

MySQL 中的会话变量不必声明即可使用，会话变量在整个过程中有效，会话变量名以字符 “@” 作为起始字符。l例子如下。

```mysql
delimiter//
create procedure p2()
begin
set @t=1;
begin
set @t=2;
select @t;
end;
select @t;
end;
//
```



**3、为变量赋值**

MySQL 中可以使用关键字 DECLARE 来定义变量，其基本语法如下。

```mysql
DECLARE var_name[,...] type [DEFAULT value]
```

MySQL 中可以使用关键字 SET 为变量赋值，其基本语法如下。

```mysql
SET var_name=expr[,var_name=expr]...
SER mr_soft=10;
```

另外，MySQL 中还可以应用另一种方式为变量赋值，其语法结构如下。

```mysql
SELECT col_name[,...] INTO var_name[,...] FROM table_name where condition
例子如下：
SELECT tel INTO customer_tel FROM studentinfo WHERE name='LeonSK';
```



### 光标的运用

通过 MySQL 查询数据库，其结果可能为多条记录。在存储过程和函数中使用光标可以实现逐条读取结果集中的记录。光标使用包括声明光标（DECLARE CURSOR）。打开光标（OPEN CURSOR）、使用光标（FETCH CURSOR）和关闭光标（CLOSE CURSOR）。值得一提的是，光标必须声明在处理程序之前，且声明变量和条件之后。

**1、声明光标**

在 MySQL 中，声明光标仍使用关键字 DECLARE。其语法如下。

```mysql
DECLARE cursor_name CURSOR FOR select_statement
```

select_statement 是一个 SELECT 语句，返回一行或多行数据。通过上述定义来声明光标 info_of_student，其代码如下。

```mysql
DECLARE info_of_student CURSOR FOR 
SELECT sid,name,age,sex FROM studentinfo
WHERE sid=1;
```

**2、打开光标**

使用关键字 OPEN 来打开光标，其基本语法如下。

```mysql
OPEN cursor_name
```

**3、使用光标**

光标在顺利打开后，可以使用 FETCH...INTO 语句来读取数据，其语法如下。

```mysql
FETCH cursor_name INTO var_name[,var_name]...
例子：
FETCH info_of_student INTO tmp_name,tmp_tel;
```

**4、关闭光标**

使用关键字 CLOSE 可以关闭光标，其基本语法如下。

```mysql
CLOSE cursor_name
例子如下：
CLOSE info_of_student
```



## 存储过程和存储函数的调用

存储过程和存储函数都是存储在服务器的 SQL 语句的集合。要使用这些已经定义好的存储过程和存储函数就必须要通过调用的方式来实现。对存储过程和函数的操作主要可以分为调用、查看、修改和删除。

### 调用存储过程

使用 CALL 语句来调用存储过程。调用存储过程后，数据库系统将执行存储过程中的语句；然后将结果返回给输出值。CALL 语句的基本语法形式如下。

```mysql
CALL sp_name([parameter[,...]]);
```



### 调用存储函数

在 MySQL 中，存储函数的使用方法与 MySQL  内部函数的使用方法基本相同。用户自定义的存储函数与 MySQL 内部函数性质相同。区别在于，存储函数是用户自定义的，而内部函数由 MySQL 自带。其语法结构如下。

```mysql
SELECT function_name([parameter[,...]]);
创建 pro_reg 存储过程，其代码如下。
delimiter//
create procedure pro_reg(in nc varchar(50),in pwd varchar(50),in email varchar(50),in address varchar(50))
begin
insert into tb_reg(name,pwd,email,address) values (nc,pwd,email,address);
end;
//
```



## 查看存储过程和存储及函数



### SHOW  STATUS 语句

在 MySQL 中可以通过 SHOW STATUS 语句查看存储过程和存储函数的状态。其基本语法结构如下。

```mysql
SHOW {PROCEDURE | FUNCTION }STATUS[LIKE 'pattern']
```



### SHOW  CREATE 语句

MySQL 中可以通过 SHOW CREATE 语句来查看存储过程和函数的状态，其语法结果如下。

```mysql
SHOW CREATE {PROCEDURE | FUNCTION } sp_name;
例子：
show create procedure count_of_student;
```



## 修改存储过程和存储函数

MySQL 中通过 ALTER PROCEDURE 语句来修改存储过程，通过 ALTER FUNCTION 语句来修改存储函数。MySQL 中修改存储过程和存储函数的语句形式如下。

```mysql
ALTER {PROCEDURE | FUNCTION} sp_name [characteristic...]
characteristic:
{CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA}
|SQL SECURITY {DEFAULT | INVOKER}
| COMMENT 'string'
```

| 参数                                | 说明                                                         |
| ----------------------------------- | ------------------------------------------------------------ |
| sp_name                             | 存储过程或函数的名称                                         |
| characteristic                      | 指定存储函数的特性                                           |
| CONTAINS SQL                        | 表示子程序包含 SQL 语句，但不包含读写数据的语句              |
| NO SQL                              | 表示子程序不包含 SQL 语句                                    |
| READS SQL DATA                      | 表示子程序中包含读数据的语句                                 |
| MODIFIES SQL DATA                   | 表示子程序中包含写数据的语句                                 |
| SQL SECURITY {DEFAULT  \|  INVOKED} | 指明权限执行。DEFAULT 表示只有定义者自己才能够执行；INVOKED 表示调用者可执行 |
| COMMENT 'string'                    | 是注释信息                                                   |



## 删除存储过程和存储函数

其基本语法结构如下。

```mysql
DROP {PROCEDURE | FUNCTION} [IF EXISTS] sp_name
例子：
drop procedure count_of_student;
drop function name_of_student;
```





# 第十五章       触发器



## MySQL 触发器

