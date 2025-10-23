# 📚 Course Management System

<div align="center">

![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![WPF](https://img.shields.io/badge/WPF-Windows%20Presentation%20Foundation-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Entity Framework](https://img.shields.io/badge/Entity%20Framework%20Core-512BD4?style=for-the-badge&logo=nuget&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![XAML](https://img.shields.io/badge/XAML-0C54C2?style=for-the-badge&logo=xaml&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

A comprehensive desktop application for managing courses, students, and grades built with WPF and Entity Framework Core.

[Features](#features) • [Installation](#installation) • [Usage](#usage) • [Database](#database) • [Screenshots](#screenshots)

</div>

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Technologies](#technologies)
- [System Architecture](#system-architecture)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Key Components](#key-components)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 About

The **Course Management System** is a powerful desktop application designed for educational institutions to manage student enrollments, course assignments, and grade tracking. Built with modern .NET technologies, it provides separate interfaces for administrators and students with comprehensive data management capabilities.

### Key Highlights

- ✅ Role-based authentication (Admin/Student)
- ✅ Real-time grade management
- ✅ Student-course enrollment tracking
- ✅ Advanced filtering and search
- ✅ Intuitive and responsive UI
- ✅ Comprehensive data validation

---

## ✨ Features

### 🔐 Authentication System
- **Secure Login**
  - Username and password validation
  - Role-based access control
  - Custom styled UI with rounded corners
  - Real-time error messages

### 👨‍💼 Administration Dashboard
- **Student Management**
  - View all students enrolled in courses
  - Filter by student or course
  - Advanced search capabilities
  - Composite key support for student-course relationships

- **Grade Management**
  - Assign grades to students (0-100 scale)
  - Update existing grades
  - Decimal precision (up to 2 decimal places)
  - Real-time validation

- **Data Filtering**
  - Filter by student name
  - Filter by course name
  - Combined filtering options
  - Load all records option

- **Modern UI Features**
  - Professional dashboard design
  - Drop shadow effects
  - Rounded borders
  - Status bar with color-coded messages
  - Responsive data grid

### 📖 Student Dashboard
- **Personal Information**
  - View enrolled courses
  - Check assigned grades
  - Course details display
  - User-friendly interface

- **Course Overview**
  - List of all enrolled courses
  - Grade status for each course
  - Course descriptions
  - Alternating row colors for readability

---

## 🛠️ Technologies

| Technology | Version | Purpose |
|------------|---------|---------|
| ![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?style=flat-square&logo=dotnet) | 8.0+ | Framework |
| ![WPF](https://img.shields.io/badge/WPF-Desktop-0078D4?style=flat-square&logo=windows) | Latest | User Interface |
| ![C#](https://img.shields.io/badge/C%23-12.0-239120?style=flat-square&logo=c-sharp) | 12.0 | Programming Language |
| ![EF Core](https://img.shields.io/badge/EF%20Core-8.0-512BD4?style=flat-square&logo=nuget) | 8.0+ | ORM |
| ![SQL Server](https://img.shields.io/badge/SQL%20Server-2019+-CC2927?style=flat-square&logo=microsoft-sql-server) | 2019+ | Database |
| ![XAML](https://img.shields.io/badge/XAML-2023-0C54C2?style=flat-square) | - | UI Markup |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     Presentation Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │    Login     │  │    Admin     │  │   Student    │      │
│  │   Window     │  │  Dashboard   │  │  Dashboard   │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                      Business Logic                          │
│  ┌──────────────────────────────────────────────────────┐   │
│  │         Entity Framework Core (Code First)           │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                       Data Layer                             │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐           │
│  │   Users    │  │  Courses   │  │  Student   │           │
│  │   Table    │  │   Table    │  │  Courses   │           │
│  └────────────┘  └────────────┘  └────────────┘           │
└─────────────────────────────────────────────────────────────┘
```

---

## 📦 Prerequisites

Before running this application, ensure you have:

### Required Software

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0) or later
- [Visual Studio 2022](https://visualstudio.microsoft.com/) (Community, Professional, or Enterprise)
  - Workload: .NET Desktop Development
  - Workload: Data storage and processing
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) 2019 or later
  - SQL Server Express (free) is sufficient
- [SQL Server Management Studio (SSMS)](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms) (Optional but recommended)

### Required NuGet Packages

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore" Version="8.0.0" />
  <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="8.0.0" />
  <PackageReference Include="Microsoft.EntityFrameworkCore.Tools" Version="8.0.0">
    <PrivateAssets>all</PrivateAssets>
    <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
  </PackageReference>
</ItemGroup>
```

---

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/course-management-system.git
cd course-management-system
```

### Step 2: Open in Visual Studio

1. Open `CoursesManagementSYS.sln` in Visual Studio 2022
2. Visual Studio will automatically restore NuGet packages
3. Wait for the restore process to complete

### Step 3: Configure Database Connection

Open `CourseManagementDB.cs` and update the connection string:

```csharp
protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
{
    string con = "Data Source=YOUR_SERVER_NAME\\SQLEXPRESS;Initial Catalog=CourseManagementDB;Integrated Security=True;Trust Server Certificate=True";
    if (!optionsBuilder.IsConfigured)
    {
        optionsBuilder.UseSqlServer(con);
    }
}
```

**Replace `YOUR_SERVER_NAME` with your SQL Server instance name.**

#### Finding Your SQL Server Name:
- Open SQL Server Management Studio
- The server name is shown in the login dialog
- Common formats:
  - `localhost\SQLEXPRESS`
  - `(localdb)\MSSQLLocalDB`
  - `COMPUTERNAME\SQLEXPRESS`

---

## 🗄️ Database Setup

### Method 1: Using Package Manager Console (Recommended)

1. Open **Package Manager Console** in Visual Studio:
   - Tools → NuGet Package Manager → Package Manager Console

2. Run the following commands:

```powershell
# Create initial migration
Add-Migration InitialCreate

# Apply migration to database
Update-Database
```

### Method 2: Using .NET CLI

```bash
# Navigate to project directory
cd CoursesManagementSYS

# Create migration
dotnet ef migrations add InitialCreate

# Apply migration
dotnet ef database update
```

---

## 📊 Database Schema

### Entity Relationship Diagram

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│     Users       │         │ StudentCourses   │         │    Courses      │
├─────────────────┤         ├──────────────────┤         ├─────────────────┤
│ UserId (PK)     │◄────────│ StudentId (FK)   │         │ CourseId (PK)   │
│ UserName        │         │ CourseId (FK)    │────────►│ CourseName      │
│ Password        │         │ Grade            │         │ Description     │
│ Role            │         │ StudentCourseId  │         └─────────────────┘
└─────────────────┘         └──────────────────┘
                            (Composite Key: 
                             StudentId + CourseId)
```

### Table Structures

#### 1. Users Table
| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| UserId | INT | Primary Key, Identity | Unique user identifier |
| UserName | NVARCHAR(50) | NOT NULL | User's login name |
| Password | NVARCHAR(100) | NOT NULL | User's password |
| Role | NVARCHAR(20) | NOT NULL, CHECK | 'Admin' or 'Student' |

#### 2. Courses Table
| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| CourseId | INT | Primary Key, Identity | Unique course identifier |
| CourseName | NVARCHAR(100) | NOT NULL | Course name |
| Description | NVARCHAR(250) | NOT NULL | Course description |

#### 3. StudentCourses Table (Junction Table)
| Column Name | Data Type | Constraints | Description |
|-------------|-----------|-------------|-------------|
| StudentCourseId | INT | Primary Key, Identity | Record identifier |
| StudentId | INT | Foreign Key, NOT NULL | References Users.UserId |
| CourseId | INT | Foreign Key, NOT NULL | References Courses.CourseId |
| Grade | DECIMAL(5,2) | NULL | Student's grade (0-100) |

**Composite Key:** (StudentId, CourseId)

---

## 💾 Seed Data

### Insert Sample Data

```sql
-- Insert Admin User
INSERT INTO Users (UserName, Password, Role) 
VALUES ('admin', 'admin123', 'Admin');

-- Insert Students
INSERT INTO Users (UserName, Password, Role) 
VALUES 
('john.doe', 'student123', 'Student'),
('jane.smith', 'student123', 'Student'),
('bob.johnson', 'student123', 'Student');

-- Insert Courses
INSERT INTO Courses (CourseName, Description)
VALUES 
('Mathematics 101', 'Introduction to Calculus and Algebra'),
('Computer Science 101', 'Programming Fundamentals with C#'),
('Physics 101', 'Classical Mechanics and Thermodynamics'),
('English Literature', 'Modern English Literature and Writing');

-- Enroll Students in Courses
-- John Doe enrollments
INSERT INTO StudentCourses (StudentId, CourseId, Grade)
VALUES 
(2, 1, 85.50),  -- Math
(2, 2, 92.00),  -- CS
(2, 3, NULL);   -- Physics (no grade yet)

-- Jane Smith enrollments
INSERT INTO StudentCourses (StudentId, CourseId, Grade)
VALUES 
(3, 1, 78.25),  -- Math
(3, 4, 88.00);  -- English

-- Bob Johnson enrollments
INSERT INTO StudentCourses (StudentId, CourseId, Grade)
VALUES 
(4, 2, 95.75),  -- CS
(4, 3, 82.50),  -- Physics
(4, 4, NULL);   -- English (no grade yet)
```

---

## 💻 Usage

### Running the Application

1. Press `F5` in Visual Studio or click the **Start** button
2. The Login window will appear

### Default Login Credentials

#### Admin Account
```
Username: admin
Password: admin123
Role: Administrator
Access: Full grade management and student oversight
```

#### Student Accounts
```
Username: john.doe
Password: student123
Role: Student
Access: View personal courses and grades
```

```
Username: jane.smith
Password: student123
Role: Student
```

---

## 🎮 User Workflows

### Admin Workflow

#### 1. Login
- Enter admin credentials
- Click "Login"
- Redirected to Administration Dashboard

#### 2. View All Enrollments
- Dashboard loads all student-course records automatically
- View StudentCourseId, Student Name, Course Name, and Current Grade

#### 3. Filter Data
**Option A: Filter by Student**
- Select student from "Select Student" dropdown
- System automatically shows that student's courses

**Option B: Filter by Course**
- Select course from "Select Course" dropdown
- Click "Load Data"
- System shows all students in that course

**Option C: Combined Filter**
- Select both student and course
- Click "Load Data"
- Shows specific enrollment record

**Option D: Reset Filter**
- Clear both dropdowns
- Click "Load Data"
- Shows all records

#### 4. Update Grades
- Select a student-course record from the data grid
- Enter grade in "Enter Grade" textbox (0-100)
- Click "Update Grade"
- Grade is saved with 2 decimal precision
- Status bar shows confirmation message

#### 5. Logout
- Click "Logout" button
- Returns to login screen

---

### Student Workflow

#### 1. Login
- Enter student credentials
- Click "Login"
- Redirected to Student Information page

#### 2. View Courses
- See personalized greeting: "Hello, [StudentName]"
- View all enrolled courses in data grid
- See assigned grades for each course
- "Not Assigned" shown for courses without grades

#### 3. Return to Login
- Click "Back" button
- Logout and return to main screen

---

## 📁 Project Structure

```
CoursesManagementSYS/
│
├── Model/
│   ├── CourseManagementDB.cs      # DbContext and database configuration
│   ├── Users.cs                   # User entity (Admin/Student)
│   ├── Courses.cs                 # Course entity
│   └── StudentCourses.cs          # Junction table for many-to-many
│
├── Views/
│   ├── Login.xaml                 # Login window UI
│   ├── Login.xaml.cs              # Login business logic
│   ├── Administration.xaml        # Admin dashboard UI
│   ├── Administration.xaml.cs     # Admin dashboard logic
│   ├── StudentInformation.xaml    # Student view UI
│   └── StudentInformation.xaml.cs # Student view logic
│
├── App.xaml                       # Application resources and styles
├── App.xaml.cs                    # Application startup configuration
├── CoursesManagementSYS.csproj    # Project file
└── CoursesManagementSYS.sln       # Solution file
```

---

## 🔑 Key Components

### 1. **Composite Key Implementation**

The system uses a composite key for `StudentCourses`:

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity<StudentCourses>()
        .HasKey(x => new { x.StudentId, x.CourseId });
}
```

This ensures:
- A student can't enroll in the same course twice
- Database integrity is maintained
- Efficient querying with composite indexes

### 2. **Role-Based Navigation**

```csharp
if (user.Role == "Admin")
{
    new Administration().Show();
    this.Close();
}
else if (user.Role == "Student")
{
    new StudentInformation(user.UserId).Show();
    this.Close();
}
```

### 3. **Dynamic Data Filtering**

```csharp
var query = db.StudentCourses
    .Include(sc => sc.Student)
    .Include(sc => sc.Course)
    .AsQueryable();

if (StudentComboBox.SelectedValue != null)
{
    int studentId = (int)StudentComboBox.SelectedValue;
    query = query.Where(sc => sc.StudentId == studentId);
}

if (CourseComboBox.SelectedValue != null)
{
    int courseId = (int)CourseComboBox.SelectedValue;
    query = query.Where(sc => sc.CourseId == courseId);
}
```

### 4. **Eager Loading with Include**

```csharp
var studentCourses = db.StudentCourses
    .Include(sc => sc.Student)  // Load student data
    .Include(sc => sc.Course)   // Load course data
    .Where(sc => sc.StudentId == _Stdid)
    .Select(sc => new { ... })
    .ToList();
```

### 5. **Grade Validation**

```csharp
if (!decimal.TryParse(GradeTextBox.Text, out decimal gradeValue) || 
    gradeValue < 0 || gradeValue > 100)
{
    StatusLabel.Content = "Grade must be between 0 and 100";
    return;
}
```

---

## 🎨 UI Highlights

### Admin Dashboard Features
- **Professional Design**
  - Blue header with white text (#4A90E2)
  - Drop shadows for depth
  - Rounded corners (CornerRadius: 8-10)
  - Status bar with color-coded messages

- **Data Grid Styling**
  - Alternating row backgrounds
  - Hover effects
  - Custom header styles
  - Center-aligned headers
  - Professional fonts (Segoe UI)

- **Interactive Elements**
  - Hand cursor on buttons
  - Opacity changes on hover
  - Real-time status updates
  - Color-coded feedback (Green: Success, Red: Error, Orange: Warning)

### Student Dashboard Features
- **Clean Interface**
  - Cornflower blue header
  - Personal greeting
  - Easy-to-read data grid
  - Alternating row colors (Gray/White)

- **DataGrid Customization**
  - Bold headers with gray background
  - Black borders for clear separation
  - Read-only mode for data integrity
  - Single selection mode

---

## 🔧 Advanced Features

### 1. **Anonymous Type Projection**
Improves performance by selecting only needed data:

```csharp
.Select(sc => new
{
    sc.StudentCourseId,
    StudentName = sc.Student.UserName,
    CourseName = sc.Course.CourseName,
    Grade = sc.Grade.HasValue ? sc.Grade.Value.ToString("F2") : "Not Assigned"
})
```

### 2. **Conditional Formatting**
```csharp
Grade = sc.Grade.HasValue ? sc.Grade.Value.ToString("F2") : "Not Assigned"
```

### 3. **Cascading Dropdowns**
Student selection automatically filters courses

### 4. **Session Management**
User ID passed between windows to maintain context

---

## 🐛 Known Issues & Solutions

| Issue | Solution |
|-------|----------|
| Connection string error | Update server name in CourseManagementDB.cs |
| Migration fails | Ensure SQL Server is running |
| Grade not updating | Check StudentCourseId is correct |
| Dropdown empty | Ensure seed data is inserted |

---

## 🚧 Future Enhancements

- [ ] Password encryption (hashing)
- [ ] Email notifications for grade updates
- [ ] Course capacity management
- [ ] Attendance tracking
- [ ] Report generation (PDF/Excel)
- [ ] Multi-semester support
- [ ] Course prerequisite management
- [ ] Student profile pictures
- [ ] Grade history and analytics
- [ ] Dark mode theme
- [ ] Export data functionality
- [ ] Advanced search with multiple criteria

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

### How to Contribute

1. **Fork the Repository**
```bash
git clone https://github.com/yourusername/course-management-system.git
```

2. **Create a Feature Branch**
```bash
git checkout -b feature/AmazingFeature
```

3. **Commit Your Changes**
```bash
git commit -m 'Add some AmazingFeature'
```

4. **Push to the Branch**
```bash
git push origin feature/AmazingFeature
```

5. **Open a Pull Request**

### Coding Standards

- Follow C# naming conventions (PascalCase for classes, camelCase for variables)
- Add XML comments for public methods
- Write meaningful commit messages
- Test thoroughly before submitting
- Update documentation for new features

---

## 📄 License

This project is licensed under the MIT License.

```
MIT License

Copyright (c) 2025 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 👥 Authors & Contributors

- **Eng-ahmed-dev1 ** - *Initial work* - [GitHub](https://github.com/Eng-ahmed-dev1 )

See also the list of [contributors](https://github.com/yourusername/course-management-system/contributors) who participated in this project.

---

## 🙏 Acknowledgments

- Microsoft for .NET and Entity Framework Core
- WPF community for design patterns
- Stack Overflow community
- All contributors and testers

---

## 📧 Contact & Support

### Get in Touch


- 🐙 GitHub: [@yourusername](https://github.com/Eng-ahmed-dev1 )

### Report Issues

Found a bug? Please open an issue on GitHub with:
- Detailed description
- Steps to reproduce
- Expected vs actual behavior
- Screenshots (if applicable)

---

## 📚 Additional Resources

- [.NET Documentation](https://docs.microsoft.com/en-us/dotnet/)
- [Entity Framework Core Docs](https://docs.microsoft.com/en-us/ef/core/)
- [WPF Tutorial](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/)
- [C# Programming Guide](https://docs.microsoft.com/en-us/dotnet/csharp/)

---

<div align="center">

### ⭐ If you find this project helpful, please give it a star!

Made with ❤️ using .NET, WPF, and Entity Framework Core

**[⬆ Back to Top](#-course-management-system)**

</div>
