---
layout: post
title: "$X กับเงื่อนไข IN หรือ NOTIN ใน JasperReports"
categories: [Tutorial, JasperReports]
tags: [Report, Java, SQL]
image: assets/images/posts/special-syntax-x-jasperreports/cover.jpg
description: "วิธีใช้ $X ใน JasperReports"
featured: true
hidden: true
---

ตัวอย่าง ต้องการค้นหาชื่อนักเรียนจากตาราง Student โดย set ของชื่อนักเรียน Steve, Tony, Thor

> SELECT * FROM STUDENT WHERE STUDENT_NAME IN ('Steve','Tony','Thor')

เมื่อใช้ special syntax ($X) จะได้เป็น

> SELECT * FROM STUDENT WHERE $X{IN, STUDENT_NAME, myList}

โดย $X{} จะมี 3 parameter

1. Type of function เช่น IN หรือ NOTIN

2. Field name เช่น STUDENT_NAME

3. Parameter ที่รับเข้ามา โดย type เป็น java.util.Collection เช่น myList ($P{myList})

---
 หาก parameter ที่รับเข้ามาเป็น null หรือ empty list ประโยคเงื่อนไข $X{} ก็จะกลายเป็น true statement ทันที

---