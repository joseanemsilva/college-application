<h1 align='center'> 
  Clinic Database System
</h1>

<p align="center">
  Project built with <br/>
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white">
</p><br/>

## About The Project 
The group project was developed as part of the Object Oriented Programming course - COMP1202, and the purpose was to develop an application for a college that has multiple courses, and the student could register for the courses. The system has a menu to display student or college information, register students on courses, display all registrations, be able to save the information to a file, and load the information.

The requirement was to build a menu-driven console application in C#. The application will simulate a simple “Course Registration System” for a small college. The focus was to work and consolidate OOP knowledge, specially:
1. Creating and using classes;
2. Using aggregating relationship;
3. Storing and manipulating data in a 2D array of objects;
4. Saving to and reading data from a file.

To implement all the requirements, we created four classes, which are: Registration, Courses, Student and College, and each one is important for the application to run and facilitates the possibility of working with the data and manipulate each object. Each class has its own attributes, constructors, and methods giving us the possibility to perform specific actions to the specific classes, such as displaying information, or counting the total of registrations, to name a few.

## Classes Description
### Student Class
The student class has the attributes id, name and email address. Its default constructor, it is used by the program class to create new instances, which are kept in a list of students at the college class. It also has a display student method which shows the student information.  The id is implemented as an auto incremented value, and when a new student is created.

### Course Class 
The course class has the attributes id, name and credit hours. Its default constructor is used by the program class to create new instances, which are kept in a list of courses at the college class. It has two methods, one to display course information and another to check if a course has full credit hours. The id is also auto incremented value when a new course is created. 

### Registration Class
The registration class was created to be able to pass the information to College.AddRegistration() method. It has the student id and course id as attributes, and the values are entered by the user when registering a specific student on a course. Its default constructor is used by the program class to create new instances, which are used to create a 2D array list containing students as rows, and courses as columns, at the college class. It also has another constructor with studentId and courseId as arguments, which is used to load the data in the program class.

### College Class
The college class has a list of students, courses, and a 2D array list of registrations. The lists are instantiated inside the college class. It has four methods: AddStudent(), which has Student as argument. It will take the student added in students and passes to the college students list, and also to the registrations list, as a new row. The method AddCourse(), has Course as argument, and a bool variable as arguments. It takes the course added in course and passes to the college courses list, and it will also call the IsFullCreditCourse() method to display if a course added has full credit or not, but the message should not be displayed when the file is loaded.

The method AddRegistration() has registration and a bool variable as parameters. It maps the index to save the student Id 1 on the variable index, to be the first row, index 0 on the registrations list. For the row, it will add the correspondent course it as enrolled course for the respective student. The method CountTotalRegistrations() will be called when registering a student for a course and display the total registrations to the college, but the message should not be shown when the file is loaded. The CountTotalRegistration() method will count the number of registrations when a registration is made, and it will output for the user to see the number of registrations made.

### 2D Array Design
In the assignment handout, it was recommended a few approaches for the 2D Array. However, we decided to make it simpler by using a List<List<int>> signature. This way, each List<int> represents the courses in which a given student is registered, and different students can be registered in a different number of courses. If we had an array MxN for M students and N courses, we would have to add an extra column every time a new course was added. By keeping it in a list, there is no extra work on course addition, and we add an empty list when a new student is added, representing the courses in which that student is registered (none, initially). 

To access the registrations for a given student, we mapped the index on the initial list to the student numbers. Student numbers start in 1, so we are using the mapping index = student –1. I.e., registrations[0] represents the courses in which student #1 is registered, registrations[1] represents the courses in which student #2 is registered and it follows. 

Finally, for a method that traverses the registrations 2D array, we implemented CountTotalRegistration() method, which counts how many registrations in total the college has. It consists of summing the length of the registration array for each student, producing the overall registrations count.

## College Application UML Diagram
  <img align="center" src="/.img/collegeApp_UML.png" width="780">