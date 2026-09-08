# C#-I Programming Re-Exam

---

## Part 1: Variable & Data Types

### Task 1 — Student Information

បង្កើត C# Console Application មួយ ហើយប្រកាស Variables សម្រាប់រក្សាទុកព័ត៌មានសិស្សម្នាក់៖

- `name` → ឈ្មោះសិស្ស
- `age` → អាយុ
- `score` → ពិន្ទុ
- `passed` → ស្ថានភាពជាប់/ធ្លាក់

បន្ទាប់មកបង្ហាញព័ត៌មានទាំងអស់តាមរយៈ `Console.WriteLine()`។

**Expected Output Example:**

```text
Student Information
-------------------
Name   : Dara
Age    : 20
Score  : 85.5
Passed : True
```

### Task 2 — Data Types

ប្រើ Data Type ឱ្យបានត្រឹមត្រូវសម្រាប់ Variables ខាងក្រោម៖

- Student Name
- Student Age
- Student Score
- Student Passed

---

## Part 2: Array

### Task 3 — Student Array

បង្កើត Array មួយដែលមានឈ្មោះសិស្សចំនួន **3 នាក់**។

ឧទាហរណ៍៖

```text
Dara
Sokha
Rina
```

បន្ទាប់មកបង្ហាញឈ្មោះសិស្សទាំង 3 នាក់។

### Task 4 — First & Last Element

ពី Array ខាងលើ៖

1. បង្ហាញ Student ដំបូង
2. បង្ហាញ Student ចុងក្រោយ

**Expected Output:**

```text
First Student : Dara
Last Student  : Rina
```

### Task 5 — Loop Through Array

ប្រើ `for` loop ដើម្បីបង្ហាញ Student ទាំងអស់នៅក្នុង Array។

**Expected Output:**

```text
Student List
------------
1. Dara
2. Sokha
3. Rina
```

---

## Part 3: Loop & If...Else

### Task 6 — For Loop

បង្កើតកម្មវិធីមួយដែលបង្ហាញលេខពី **1 ដល់ 10** ដោយប្រើ `for` loop។

```text
1
2
3
...
10
```

### Task 7 — While Loop

ប្រើ `while` loop ដើម្បីបង្ហាញលេខពី **10 ដល់ 1**។

```text
10
9
8
...
1
```

### Task 8 — If...Else

បង្កើត Variable មួយសម្រាប់រក្សាទុកពិន្ទុសិស្ស៖

```csharp
double score = 75;
```

ប្រើ `if...else` ដើម្បីពិនិត្យ៖

- Score >= 50 → `Pass`
- Score < 50 → `Fail`

**Expected Output:**

```text
Score: 75
Result: Pass
```

---

## Part 4: Method / Function

### Task 9 — Create a Method

បង្កើត Method មួយឈ្មោះ៖

```csharp
ShowStudent()
```

Method នេះត្រូវបង្ហាញ៖

```text
Name: Dara
Age: 20
```

បន្ទាប់មកហៅ Method ពី `Main()`។

### Task 10 — Parameter & Argument

បង្កើត Method៖

```csharp
ShowStudent(string name, int age)
```

ហើយហៅ Method ដូចជា៖

```csharp
ShowStudent("Dara", 20);
ShowStudent("Sokha", 21);
```

**Expected Output:**

```text
Name: Dara
Age: 20

Name: Sokha
Age: 21
```

### Task 11 — Return Value

បង្កើត Method៖

```csharp
int Add(int a, int b)
```

Method ត្រូវបូកលេខពីរ ហើយ `return` លទ្ធផល។

ឧទាហរណ៍៖

```csharp
int result = Add(10, 20);
Console.WriteLine(result);
```

**Expected Output:**

```text
30
```

---

## Part 5: List<T>

### Task 12 — Create Student List

បង្កើត `List<string>` មួយដែលមានឈ្មោះសិស្សចំនួន **5 នាក់**។

ឧទាហរណ៍៖

```text
Dara
Sokha
Rina
Vanna
Bora
```

### Task 13 — Add & Remove

ប្រើ `Add()` ដើម្បីបន្ថែម Student ថ្មីម្នាក់ទៅក្នុង List។

បន្ទាប់មក៖

- ប្រើ `Remove()` ដើម្បីលុប Student ម្នាក់តាមឈ្មោះ
- ប្រើ `RemoveAt()` ដើម្បីលុប Student តាម Index

### Task 14 — First & Last Item

បង្ហាញ៖

```text
First Student
Last Student
```

ដោយយកពី `List`។

**Expected Output:**

```text
First Student: Dara
Last Student: Bora
```

### Task 15 — foreach Loop

ប្រើ `foreach` ដើម្បីបង្ហាញ Student ទាំងអស់នៅក្នុង List។

**Expected Output:**

```text
Student List
------------
Dara
Sokha
Rina
Vanna
Bora
```

---

## Part 6: Built-in Functions

### Task 16 — Built-in Functions

បង្កើតកម្មវិធីមួយដែលប្រើ **យ៉ាងហោចណាស់ 5 Built-in Functions/Methods** របស់ C#។

ឧទាហរណ៍ដែលអាចប្រើ៖

```csharp
Math.Max()
Math.Min()
Math.Round()
string.ToUpper()
string.ToLower()
string.Contains()
string.Length
```

បង្កើត Output ដែលបង្ហាញលទ្ធផលនៃ Function/Method ទាំងនោះ។

**Example:**

```text
Maximum : 100
Minimum : 20
Rounded : 85
Upper   : DARA
Lower   : dara
```

---

## Task 17 — Student Score Management System

បង្កើតកម្មវិធី C# Console Application តូចមួយសម្រាប់គ្រប់គ្រង Student។

កម្មវិធីត្រូវមាន៖

```text
===== Student Management =====

1. Add Student
2. Show Students
3. Remove Student
4. Search Student
5. Exit
```

### Requirements

ត្រូវប្រើ៖

- `List<T>`
- `Method`
- `Parameter`
- `Return`
- `if...else`
- `while` ឬ `do...while`
- `foreach`
- Built-in method

### Example

```text
===== Student Management =====

1. Add Student
2. Show Students
3. Remove Student
4. Search Student
5. Exit

Choose option: 1

Enter student name: Dara

Student added successfully!
```

បើជ្រើស `2`៖

```text
Student List
------------
1. Dara
2. Sokha
3. Rina
```

## 🚨🚨លក្ខខណ្ឌ⚠️⚠️

សម្រាប់ **គ្រប់ Task នីមួយៗ** សិស្សត្រូវ **បង្ហាញការដំណើរការកូដដោយផ្ទាល់** និង **វីដេអូនៃការបង្ហាញកូដ**។

ក្នុងអំឡុងពេលបង្ហាញ សិស្សត្រូវ៖

* ដំណើរការកម្មវិធី និងបង្ហាញលទ្ធផល។
* ពន្យល់អំពីផ្នែកសំខាន់ៗនៃកូដដែលបានសរសេរ។
* បង្ហាញថាកម្មវិធីអាចដំណើរការបានត្រឹមត្រូវតាមតម្រូវការ។
* ឆ្លើយសំណួររបស់គ្រូទាក់ទងនឹងការអនុវត្ត និងដំណើរការរបស់កូដ។

វីដេអូ ត្រូវបង្ហាញឱ្យបានច្បាស់អំពី **កូដ ការដំណើរការកម្មវិធី និងការពន្យល់**។

---
