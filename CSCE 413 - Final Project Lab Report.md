<a name="br1"></a> 

**Final Project: School Management System**

Written by:

**Ben Morales**

**Mohamed Abbas**

**Raoul Nya**

**DATABASE SYSTEMS - FALL 2023**



<a name="br2"></a> 

School Management System

2

**GOALS**

In today's fast-paced educational landscape, the demand for efficient,

user-friendly, and comprehensive school management systems has never been

greater. Our School Management System Project is designed to meet this demand

by delivering a versatile platform that streamlines administrative tasks, enhances

communication, and fosters an environment of collaborative learning.

The intended use of our School Management System is to collect and

manipulate a wide collection of data from students, instructors, and the school

itself in order to provide real-time updates on academic progress, and to both

simplify and automate aspects within educational management to improve

efficiency, minimize human error, and ultimately to allow educators to put more

focus on teaching rather than paperwork and the structuring of classes.

The intended users of this database system include students, instructors,

administrative staff, and faculty leadership. Students mainly benefit from accessing

class schedules, registering for classes, viewing academic records, tracking

attendance and managing personal information. Instructors or professors use it to

manage courses, view student rosters, enter grades, schedule courses, and access

academic resources. University administrative staff manage admissions, manage

student records, assign classrooms, coordinate schedules, and generate reports on



<a name="br3"></a> 

School Management System

3

academic performance and institutional statistics. Faculty management uses the

system to manage the physical infrastructure of the university, including

classrooms, lecture halls, laboratories and other facilities, schedule maintenance,

track equipment and manage room assignments for the class.

The database system offers a variety of services tailored to the needs of its

users. These include course management, where students can search, register for

courses, view their course schedules, and access course information. Classroom

management focuses on the efficient allocation of classrooms for different courses

and academic activities. Resource coordination involves the coordination of

resources for academic purposes, such as laboratories, equipment, and library

materials. Reporting and analytics is also a key service, enabling reporting on

student performance, enrollment statistics and other relevant institutional data.



<a name="br4"></a> 

School Management System

4

**DATABASE DESIGN AND DATA**

Our School Management System will compare and transform collected data

of instructors, students, and the classes held between the two. Data such as

students’ majors and years, instructors’ departments and degrees, will be collected.

Students and instructors will be connected by the classes that they attend and teach

respectively. With the design structured as such, it will be easier to determine and

retrieve relevant information about the current academic pathways both parties are

taking.

**- Entity-Relationship Diagram (ERD)**

This entity-relationship diagram (ERD) provides a comprehensive visual

representation of the database structure of our academic management system. It

delineates the complex relationships between various entities such as students,

classes, instructors, and classrooms. Each entity is symbolized by a set of



<a name="br5"></a> 

School Management System

5

attributes, illustrating the data we collect and maintain to support our educational

goals. The ERD serves as a blueprint for database design, ensuring that the system

accurately reflects the complex operations of our academic institution. It facilitates

efficient organization of information and supports features required by students,

faculty, and administrative staff.

**- Tables**

Student

Class

Instructor Instructor\_Location Class\_Room

Id

Id

Id

Id

x

Id

First\_Name Subject

First\_Name

Last\_Name

Capacity

Last\_Name Size\_Limit

y

Room\_Number

Major

Class\_Room\_Id Department

Building\_Id

Standing

Degree

Type

x

y

x

y

Teach

Attend

Instructor\_Id

Class\_Id

Student\_Id

Class\_Id

Day

Starting\_Time

Ending\_Time



<a name="br6"></a> 

School Management System

6

Find\_Distance Find\_Time

Campus UNL Entry

a

distance

time

id

x

id

x

id

x

b

c

y

y

y

d

distance

**- Data in MLPQ**

All entities and functions unselected:

Dummy data for “Student” entity:

Dummy data for “Class” entity:



<a name="br7"></a> 

School Management System

7

Dummy data for “Class\_Room” entity:

Dummy data for “Teach” relational entity:



<a name="br8"></a> 

School Management System

8

Dummy data for “Attend” relational entity:

Constraint visualizations of “Campus” and “UNL” constraint entities:

Constraint tables for “UNL” entity buildings:



<a name="br9"></a> 

School Management System

9

“Entry” tables showcasing IDs and coordinates of building entrances:

“Find\_Distance” function table showing the utilization of entry point

coordinates to determine distance between two buildings:



<a name="br10"></a> 

School Management System

10

“Find\_Time” function table showing the estimation of how much time will

pass for the average person to walk a given distance. Average walking speed set at

80 m/s:

Constraint mapping of campus and buildings (in meters):



<a name="br11"></a> 

School Management System

11

**FUNCTIONS AND IMPLEMENTATION**

We defined three high-level functions that can help our end-users:

**- Function One: Time-Distance Estimation**

Through queries and functions, our database can determine the approximate

time an instructor will make it from one given classroom to another.

Through the data our database collects, one can find the class IDs of all

classes a specific instructor teaches:



<a name="br12"></a> 

School Management System

12

In addition to those class IDs, one can also find the day, start time, and end

time those classes take place:

One can then find the desired classroom IDs for the two classes they wish to

estimate the time it will take the instructor that teaches both to make it from one to

the next:



<a name="br13"></a> 

School Management System

13

With the classroom IDs determined, one can then find their respective

building IDs:



<a name="br14"></a> 

School Management System

14

With the buildings determined, the user can then use the x and y positions of

the two desired buildings’ entry points within the Find\_Distance function to find

the distance in meters:

Then, that found distance can be input into the Find\_Time function to

approximate the time it would take the instructor to go from one classroom to

another in minutes.



<a name="br15"></a> 

School Management System

15

In this case, it is determined that the instructor moving from class **ID 3** and

class **ID 8** will make it from one classroom to the next in approximately **16.875**

**minutes**. Seeing that the end time of the first class and the start time of the second

class is a 15 minute timeframe, it would be advisable to reschedule the instructor’s

taught classes so as to better accommodate his or her ability to make it to each

class on time.

**- Function Two: Office-Building Locating**

The UNL constraint entity (of which would differ and have a different name

for different locations) maps the layout of each building on campus. Using the x

and y coordinates of an instructor’s office, the ID of the building the office is

located can be determined:



<a name="br16"></a> 

School Management System

16

**- Function Three: Student Schedule Listing**

Through the data collected for the database, a student’s schedule can

efficiently be queried. One can easily find all class IDs of any given student:

With more depth, schedules with class names, start and end times, and the

day of each class can all be shown together:



<a name="br17"></a> 

School Management System

17

