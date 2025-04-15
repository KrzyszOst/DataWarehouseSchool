# 🏫 School Data Warehouse Design

This project was created for a **Data Warehousing** course.  
It presents a fully designed dimensional data warehouse tailored for managing and analyzing key school-related processes such as classes, attendance, surveys, exams, and meetings.

---

## 🎯 Project Scope

The goal was to design a star-schema warehouse structure to support multidimensional analysis on various school activities, enabling easy querying and reporting through OLAP tools.

---

## 🧱 Data Warehouse Structure

### ✅ Fact Tables

- **📖 `Meeting`** – Contains info on when, where, and by whom a class was conducted  
- **🧪 `Exam`** – Stores student exam results with related course, class, and room data  
- **📋 `Survey`** – Includes survey scores submitted by students  
- **🚫 `Attendance`** – Captures records of student absences, with context

### ✅ Dimension Tables

- **`Class`** – Class ID, name, specialization  
- **`Student`** – Personal info, gender, district  
- **`Teacher`** – Personal info, gender, district  
- **`Classroom`** – Room ID, number, floor  
- **`Course`** – Course name, year  
- **`Date`** – Full calendar support with hierarchies  
- **`Time`** – Hour, minute, time of day  
- **`Circumstances`** – Reason/notes for absences (excused, late, etc.)

---

## 📊 Analytical Use Cases

The model supports a variety of queries such as:

- Average **exam scores** per class, course, gender, or city  
- **Survey feedback** per specialization or student  
- **Attendance and lateness rates** per teacher, city, or top-performing students  
- Impact of **room or time** on exam results  
- Class-based or teacher-based **performance tracking**

---

## 📈 Hierarchies

- **Time Hierarchy:** TimeOfDay → Hour → Minute  
- **Date Hierarchy:** Year → MonthNumber → DayNumber

---

## 📂 Data Sources

The warehouse integrates data from:

- `SchoolMaster` relational DB  
- `Attendance.csv` file  
- Auto-generated dimension tables for `Date` and `Time`

---

## 📋 Summary

This multidimensional model enables efficient analysis of the educational process by providing structured views of attendance, academic performance, and engagement metrics. It follows star schema best practices, supports slowly changing dimensions (SCD1), and includes clear granularity definitions for each fact table.

---

**Authors:** Krzysztof Ostrzycki & Miłosz Grunwald
