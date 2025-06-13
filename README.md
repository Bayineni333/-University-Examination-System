# University Examination System Database

## 📚 Project Description

This project is a **University Examination System Database** designed to manage and track information related to exams, students, professors, courses, and departments.  
It maintains relationships between entities to enable efficient storage, retrieval, and management of data in a realistic university setting.

---

## 🔹 ER Schema 🔹

The ER Schema comprises the following entities and relationships:

- **Department**:
  - Primary Key: `dept_name`
  - Head (Faculty) : `head_faculty_id`

- **Faculty**:
  - Primary Key: `emp_id`
  - Each faculty can:
    - Head a department
    - Teach multiple courses
    - Coordinate a course

- **Course**:
  - Primary Key: `course_code`
  - Foreign Keys:
    - `dept_name` → Department
    - `coordinator_id` → Faculty
  - Each course belongs to a department.

- **FacultyCourse** (Teaching Assignments):
  - Composite Primary Key: `(emp_id, course_code)`
  - Foreign Keys:
    - `emp_id` → Faculty
    - `course_code` → Course

- **Student**:
  - Primary Key: `roll_number`
  - Foreign Key:
    - `dept_name` → Department
  
- **StudentCourse** (Enrollments and Attendance):
  - Composite Primary Key: `(roll_number, course_code)`
  - Foreign Keys:
    - `roll_number` → Student
    - `course_code` → Course
  - Stores attendance percentage for each student in each course.

- **Exam**:
  - Primary Key: `exam_id`
  - Foreign Keys:
    - `course_code` → Course
    - `created_by` → Faculty
  - Each exam belongs to a course and is created by a faculty.

- **ExamAttempt**:
  - Primary Key: `attempt_id`
  - Foreign Keys:
    - `exam_id` → Exam
    - `roll_number` → Student
  - Stores marks and attempt number for each student’s attempt in exams.

---

## 🔹 Database Schema (Table Creation Statements) 🔹

✅ All table definitions with Primary Keys, Foreign Keys, and relationships are included in the files alongside this repository (see [code files](./)).

---

## 🔹 Sample Records 🔹

The following are some sample records for each table (populating the database with realistic data), for testing and demonstration:

✅ **Departments**  
✅ **Faculty**  
✅ **Courses**  
✅ **FacultyCourse** (Teaching Assignments)  
✅ **Students**  
✅ **StudentCourse** (Enrollments with Attendance)  
✅ **Exams**  
✅ **ExamAttempts** (Student’s marks in exams)

---

## 🔹 Installation 🔹

1. clone the repository:
```bash
git clone https://github.com/yourUsername/university-examination-database.git
