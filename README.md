# Simple Projects

A collection of small C# projects and Object-Oriented Programming exercises developed using **C#**, **.NET Framework**, **Windows Forms**, and fundamental OOP concepts.

The repository contains several independent applications covering academic utilities, authentication, student management, file management, and object-oriented business logic. These projects were developed to practice software design, GUI development, class modeling, collections, inheritance, file handling, and application logic.

---

## Projects

| Project | Type | Main Concepts |
|---|---|---|
| **Build a File Manager** | Windows Forms | Classes, collections, file abstraction, CRUD-style operations |
| **CGPA Calculator** | Windows Forms | Grade calculation, collections, GPA/CGPA computation |
| **OOC Assessment** | Console Application | Inheritance, abstraction, classes, object relationships |
| **Student Enrollment Information** | Windows Forms | Classes, collections, student/department relationships |
| **Windows Forms Application Authentication System** | Windows Forms | Registration, login, file handling, multiple forms |

---

# 1. Build a File Manager

A Windows Forms application that provides a simplified simulation of a file management system.

The application represents files as objects and maintains them in an in-memory collection.

### Features

- Create and add files
- Specify file name
- Specify file type
- Store file content
- Remove files
- View file contents
- Update editable file content
- Display available file operations based on file type
- Generate a file summary
- Display total number of files
- Calculate total stored content size
- Display individual file information

### File Types

The application distinguishes between:

- `read-only`
- `editable`

Read-only files expose operations such as:

- Share
- Print
- Archive

Editable files additionally expose:

- Edit
- Translate
- Compress

### Main Classes

```text
File
Form1
Program
```

The `File` class represents an individual file with:

```text
name
type
content
```

Files are maintained using a `List<File>` collection.

### Technology

- C#
- Windows Forms
- .NET Framework 4.7.2

---

# 2. CGPA Calculator

A Windows Forms application for calculating course grades, GPA values, and overall CGPA.

The calculator accepts assessment components for individual courses and determines the corresponding grade and GPA.

### Assessment Components

The application uses:

- Midterm
- Final
- Attendance
- Four quizzes

For quizzes, the application sorts the four quiz scores and calculates the average of the **three highest scores**.

The resulting course total is then used to determine the grade and GPA.

### Grade Scale

| Total Marks | Grade | GPA |
|---:|:---:|---:|
| 80+ | A+ | 4.00 |
| 75–79 | A | 3.75 |
| 70–74 | A- | 3.50 |
| 65–69 | B+ | 3.25 |
| 60–64 | B | 3.00 |
| 55–59 | B- | 2.75 |
| 50–54 | C+ | 2.50 |
| 45–49 | C | 2.25 |
| 40–44 | D | 2.00 |
| Below 40 | F | 0.00 |

### Features

- Add course results
- Calculate total marks
- Calculate GPA for each course
- Determine letter grade
- Display course results
- Calculate overall CGPA
- Round final CGPA to two decimal places
- Clear input fields

### Main Classes

```text
Form1
Program
```

The application maintains course codes, total marks, GPA values, and grades using `List<T>` collections.

### Technology

- C#
- Windows Forms
- .NET Framework 4.7.2

---

# 3. OOC Assessment

A console-based Object-Oriented Programming exercise focused on modeling a small store and its employees.

The project demonstrates relationships between employees, products, managers, sales associates, and a store.

## Object Model

```text
Employee
   |
   +-- Manager
   |
   +-- SalesAssociate

Store
   |
   +-- Product
```

### Employee

`Employee` is an abstract base class containing common employee information such as:

- Name
- Age
- Base salary

It also provides a method for displaying employee information.

### Manager

The `Manager` class inherits from `Employee`.

Manager functionality includes:

- Adding products
- Adding inventory to existing products
- Sending inventory requisitions
- Displaying employee information

### Sales Associate

The `SalesAssociate` class also inherits from `Employee`.

It supports:

- Selling products
- Updating inventory
- Calculating sales-related bonus values

### Product

Each product contains:

- Product ID
- Product name
- Price
- Inventory level
- Minimum inventory level
- Required replenishment amount

### Store

The `Store` class maintains a collection of products and provides store-related functionality.

### Demonstration Scenario

The console application creates:

- One manager
- Two sales associates
- Three products

It then demonstrates:

1. Product creation
2. Product sales
3. Inventory updates
4. Additional inventory
5. Further sales
6. Inventory requisition
7. Employee information display

### Technology

- C#
- .NET Framework 4.7.2
- Console application
- Object-Oriented Programming

### OOP Concepts Demonstrated

- Abstraction
- Inheritance
- Encapsulation
- Classes and objects
- Object relationships
- Collections
- Method implementation

---

# 4. Student Enrollment Information

A Windows Forms application for managing students and their department enrollment information.

The application models a relationship between departments and students.

## Main Entities

### Department

Each department contains:

- Department name
- Department code
- List of enrolled students

### Student

Each student contains:

- Student ID
- Name
- Section
- Department code

## Features

- Add a department
- Assign a department code
- Add students
- Associate students with departments
- Select a department
- Display enrolled students
- Display student ID, name, department, and section

### Basic Data Relationship

```text
Department
    |
    +-- Student
    +-- Student
    +-- Student
```

Students are stored within the corresponding department's `List<Student>` collection.

### Technology

- C#
- Windows Forms
- .NET Framework 4.7.2

The project also references the **Guna.UI** WinForms framework for its interface.

---

# 5. Windows Forms Application Authentication System

A multi-form Windows Forms application implementing a basic registration and login workflow using local file-based storage.

The application consists of three main forms.

## Form Structure

```text
Form 1
Login
  |
  +---- Sign Up ----> Form 2
  |
  +---- Successful Login ----> Form 3
                              |
                              +---- Logout
```

### Login

Users provide:

- Username
- Password

The application reads the local credentials file and checks whether the supplied credentials match an existing account.

### Registration

New users can create an account by providing:

- Name
- Username
- Password
- Password confirmation

The application performs basic validation:

- Username must contain at least six characters
- Password must contain at least six characters
- Username must be unique
- Password confirmation must match

Credentials are then appended to the local credentials file.

### Welcome Screen

After successful authentication, the application opens a welcome form displaying the authenticated username.

Users can then log out and return to the login screen.

### Data Storage

User information is stored in:

```text
username&password_list.txt
```

The project uses C# file I/O operations such as:

```csharp
File.ReadAllLines()
File.AppendAllText()
```

### Main Components

```text
Form1.cs
Form2.cs
Form3.cs
Program.cs
username&password_list.txt
```

### Technology

- C#
- Windows Forms
- .NET Framework 4.7.2
- File I/O

---

# Repository Structure

```text
Simple-Projects/
│
├── Build a File Manager/
│   ├── Build a File Manager.sln
│   └── Build a File Manager/
│       ├── File.cs
│       ├── Form1.cs
│       ├── Form1.Designer.cs
│       ├── Program.cs
│       └── Properties/
│
├── CGPA Calculator/
│   ├── CGPA Calculator.sln
│   ├── CGPA Calculator.csproj
│   ├── Form1.cs
│   ├── Form1.Designer.cs
│   ├── Program.cs
│   └── Properties/
│
├── OOC Assesment/
│   └── Lab08/
│       ├── Employee.cs
│       ├── Manager.cs
│       ├── Product.cs
│       ├── SalesAssociate.cs
│       ├── Store.cs
│       ├── Program.cs
│       └── Lab08.csproj
│
├── Student Enrollment Information/
│   └── Student Enrollment Information/
│       ├── Department.cs
│       ├── Student.cs
│       ├── Form1.cs
│       ├── Form1.Designer.cs
│       ├── Program.cs
│       └── Properties/
│
└── Windows Forms Application Authentication System/
    ├── Form1.cs
    ├── Form2.cs
    ├── Form3.cs
    ├── Program.cs
    ├── username&password_list.txt
    └── lab09.csproj
```

---

# Technology Stack

### Programming Language

- C#

### Framework

- .NET Framework 4.7.2

### User Interface

- Windows Forms

### Application Types

- Desktop GUI applications
- Console applications

### Development Concepts

- Object-Oriented Programming
- Classes and objects
- Inheritance
- Abstraction
- Encapsulation
- Collections
- Event-driven programming
- File handling
- Basic application architecture
- GUI development
- Data processing

---

# Setup and Execution

These projects target **.NET Framework 4.7.2**, so a Windows development environment with Visual Studio is recommended.

## Requirements

- Windows
- Visual Studio
- .NET Framework 4.7.2
- C# development tools
- Windows Forms workload for the GUI projects

## Running a Project

1. Clone the repository.

```bash
git clone https://github.com/codebyrifaf/Simple-Projects.git
```

2. Open the required `.sln` or `.csproj` file in Visual Studio.

3. Restore/build the project if required.

4. Select the desired project as the startup project.

5. Run the application using:

```text
Ctrl + F5
```

or:

```text
F5
```

The `OOC Assessment` project is a console application, while the other projects are primarily Windows Forms applications.

---

# Educational Purpose

This repository represents a collection of smaller software projects created to practice practical programming and Object-Oriented Programming concepts.

Rather than being a single integrated application, each project focuses on a particular programming problem or development concept.

The projects demonstrate progression from basic application logic and GUI development toward more structured object-oriented modeling.

---

# Key Learning Areas

Through these projects, the repository demonstrates experience with:

- C# programming
- Windows Forms development
- Event-driven programming
- Object-oriented design
- Class inheritance
- Abstract classes
- Collections and lists
- File-based persistence
- Authentication workflows
- Form-to-form navigation
- Data validation
- Business logic implementation
- Academic result processing
- Student information management
- Inventory management concepts

---

# Project Status

These projects are **educational and portfolio-oriented applications** rather than production systems.

They were developed primarily to practice C#, .NET Framework, Windows Forms, object-oriented programming, data structures, and application logic.

Some implementations use simplified approaches such as in-memory collections or local text files because the focus is on programming concepts rather than production infrastructure.

---

# Author

**Rifaf**

Software Engineering Graduate  
Islamic University of Technology

GitHub:  
https://github.com/codebyrifaf

---

# License

This repository is intended primarily for educational and portfolio purposes. Individual projects may contain their own academic context or requirements.
