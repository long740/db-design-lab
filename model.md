\# 学生选课成绩系统 - 数据库表结构设计



\## 1. 学生表 (student)

| 字段名 | 数据类型 | 约束 | 说明 |

| :--- | :--- | :--- | :--- |

student_id | INT | PRIMARY KEY, NOT NULL | 学号（主键）

| name | VARCHAR(20) | NOT NULL | 姓名 |

| gender | VARCHAR(4) | NULL | 性别 |

| age | INT | NULL | 年龄 |



\## 2. 教师表 (teacher)

| 字段名 | 数据类型 | 约束 | 说明 |

| :--- | :--- | :--- | :--- |

| teacher\_id | INT | PRIMARY KEY, NOT NULL | 教师编号（主键） |

| name | VARCHAR(20) | NOT NULL | 教师姓名 |

| subject | VARCHAR(30) | NULL | 授课科目 |





\## 3. 课程表 (course)

| 字段名 | 数据类型 | 约束 | 说明 |

| :--- | :--- | :--- | :--- |

| course\_id | INT | PRIMARY KEY, NOT NULL | 课程号（主键） |

| course\_name | VARCHAR(50) | NOT NULL | 课程名称 |

| teacher\_id | INT | FOREIGN KEY REFERENCES teacher(teacher\_id) | 关联授课教师（外键） |





\## 4. 选课成绩表 (sc)

| 字段名 | 数据类型 | 约束 | 说明 |

| :--- | :--- | :--- | :--- |

| id | INT | PRIMARY KEY, AUTO\_INCREMENT | 选课记录ID（主键） |

| student\_id | INT | FOREIGN KEY REFERENCES student(student\_id), NOT NULL | 关联学生学号 |

| course\_id | INT | FOREIGN KEY REFERENCES course(course\_id), NOT NULL | 关联课程号 |

| score | DECIMAL(5,2) | NULL | 课程成绩（支持小数，精度为两位） |

