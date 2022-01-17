---
description: Intel 手册第三卷第四章
---

# 基本内容

## 1. 分页的作用

* paging model 将线性地址转换为物理地址
* access right 访问线性地址的权限
* memory type 地址的内存类型（cache方式）​

## 2.1. paging model

### 控制分页模型的寄存器位

* CR0的WP（bit 16）、PG（bit 31）
* CR4的PSE（bit 4）, PAE（bit 5）, PGE（bit 7）, PCIDE（bit 17）, SMEP（bit 20）, SMAP（bit 21）, PKE（bit 22）, CET（bit 23）
* IA32\_EFER MSR的LME （bit 8）、 NXE（bit 11）
* EFLAGS的AC（bit 18）
