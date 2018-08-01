# Hello-world
This is the first repository for Damon in the big family of GitHub, the best wish to everyone include me, we will get stronger from there.
pretent I made a change there...
use database0801002;
-- 创建学生表
CREATE TABLE student(
sno VARCHAR(10) PRIMARY KEY,
sname VARCHAR(10) not null,
sex VARCHAR(2) CHECK(sex="男" or sex="女"),
dept VARCHAR(10) CHECK(dept="计算机科学系"or dept="数学系"or dept="管理系"or dept="中文系"or dept="外语系"or dept="法学系"),
birth DATE,
age INT(10)
);
-- 创建成绩表
CREATE TABLE cs(
sno VARCHAR(10) PRIMARY KEY,
cno VARCHAR(10),
cj INT(3) CHECK(cj BETWEEN 0 and 100)
);
-- 创建课程表
CREATE TABLE course(
cno VARCHAR(10) PRIMARY KEY,
cname VARCHAR(10) not null
);
-- 创建cs表的Y键
ALTER TABLE cs ADD CONSTRAINT fk_cs_student FOREIGN KEY(sno)
REFERENCES student(sno);
ALTER TABLE cs ADD CONSTRAINT fk_cs_course FOREIGN KEY(cno)
REFERENCES course(cno);
