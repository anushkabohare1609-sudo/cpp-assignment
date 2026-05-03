# cpp-assignment
Anushka Bohare
soc-13
roll no 17

**Experiment – 1 **

Code with output: 
#include <iostream> // Provides input and output operations 
#include <iomanip> // Provides formatted output functions like setprecision() 
using namespace std; 
// Definition of class HotelBill 
class HotelBill 
{ 
private: 
// Data members (private for data security) 
int tableNo, items; // Stores table number and number of items 
string customerName; // Stores customer name 
long long contact; // Stores customer contact number 
f
loat total, discount, payable; // Stores bill details 
public: 
// Member function to accept customer details 
void getCustomerDetails() 
{ 
// Accept table number 
cout << "Enter Table Number: "; 
cin >> tableNo; 
// Clear input buffer before taking string input 
cin.ignore(); 
// Accept customer name (including spaces) 
cout << "Enter Customer Name: "; 
getline(cin, customerName); 
// Accept customer contact number 
cout << "Enter Customer Contact Number: "; 
cin >> contact; 
} 
// Member function to accept order details 
void getOrderDetails() 
{ 
int qty; // Quantity of each item 
f
loat price; // Price of each item 
total = 0; // Initialize total bill amount 
// Accept number of ordered items 
cout << "\nEnter Number of Items Ordered: "; 
cin >> items; 
// Loop to accept quantity and price of each item 
for (int i = 1; i <= items; i++) 
{ 
cout << "\nItem " << i << " Quantity: "; 
cin >> qty; 
cout << "Item " << i << " Price: "; 
cin >> price; 
// Calculate total amount 
total += qty * price; 
} 
} 
// Member function to calculate discount and final payable amount 
void calculateBill() 
{ 
// Apply discount based on total amount 
if (total >= 2000) 
discount = total * 0.20; // 20% discount 
else if (total >= 1000) 
discount = total * 0.10; // 10% discount 
else 
discount = 0; // No discount 
// Calculate final payable amount 
payable = total - discount; 
} 
// Member function to display the final bill 
void displayBill() 
{ 
cout << "\n---------- HOTEL BILL ----------\n"; 
cout << "Table No : " << tableNo << endl; 
cout << "Customer Name : " << customerName << endl; 
cout << "Contact Number : " << contact << endl; 
// Display bill amount with two decimal places 
cout << fixed << setprecision(2); 
cout << "Total Amount : Rs. " << total << endl; 
cout << "Discount : Rs. " << discount << endl; 
cout << "Payable Amount : Rs. " << payable << endl; 
} 
}; 
int main() 
{ 
// Create an object of HotelBill class 
HotelBill bill; 
// Call member functions using object 
bill.getCustomerDetails(); // Get customer information 
bill.getOrderDetails(); // Get order details 
bill.calculateBill(); // Calculate bill and discount 
bill.displayBill(); 
// Display final bill 
return 0; // End of program 
} 

OUTPUT : 
Enter Table Number: 5 
Enter Customer Name: Amit Sharma 
Enter Customer Contact Number: 9876543210 
Enter Number of Items Ordered: 3 
Item 1 Quantity: 2 
Item 1 Price: 250 
Item 2 Quantity: 1 
Item 2 Price: 600 
Item 3 Quantity: 3 
Item 3 Price: 300 ---------- HOTEL BILL ---------- 
Table No : 5 
Customer Name : Amit Sharma 
Contact Number : 9876543210 
Total Amount : Rs. 1850.00 
Discount : Rs. 185.00 
Payable Amount : Rs. 1665.00



**Experiment – 2: **

Program Code: 
/*WAP to demonstrate Class and object: Write a CPP program to calculate 
the percentage of n number of subject’s marks of n number of students. 
*/ 
#include <iostream> // Header file for input and output operations 
using namespace std; // To use standard namespace 
// Class definition 
class Student 
{ 
private: 
int rollNo; // Stores roll number of the student 
string name; // Stores name of the student 
string div; // Stores Division of the student 
f
loat marks[10]; // Stores marks of subjects (maximum 10) 
f
loat total; // Stores total marks 
f
loat percentage; // Stores calculated percentage 
int n; // Stores number of subjects 
public: 
// Function to accept student details and marks 
void getData() 
{ 
// Accept roll number 
cout << "\nEnter Roll Number: "; 
cin >> rollNo; 
cin.ignore(); 
// Accept name 
cout << "\nEnter name: "; 
getline(cin, name); 
// Accept div 
cout << "\nEnter Division: "; 
getline(cin, div); 
// Accept number of subjects 
cout << "Enter number of subjects: "; 
cin >> n; 
total = 0; // Initialize total to zero 
// Loop to accept marks of each subject 
for (int i = 0; i < n; i++) 
{ 
cout << "Enter marks of subject " << i + 1 << ": "; 
cin >> marks[i]; 
total = total + marks[i]; // Add marks to total 
} 
} 
// Function to calculate percentage 
void calculate() 
{ 
percentage = total / n; // Calculate percentage 
} 
// Function to display student result 
void display() 
{ 
cout << "\nRoll Number : " << rollNo; 
cout << "\nName: " << name; 
cout << "\nDivision: " << div; 
cout << "\nTotal Marks : " << total; 
cout << "\nPercentage : " << percentage << "%\n"; 
} 
}; 
// Main function 
int main() 
{ 
int stud; // Stores number of students 
// Accept number of students 
cout << "Enter number of students: "; 
cin >> stud; 
Student s[10]; // Array of objects of Student class 
// Loop for each student 
for (int i = 0; i < stud; i++) 
{ 
cout << "\n--- Student " << i + 1 << " ---"; 
s[i].getData(); // Call function to accept data 
s[i].calculate(); // Call function to calculate percentage 
s[i].display(); // Call function to display result 
} 
return 0; // End of program 
} 

Output: 
Enter number of students: 2 --- Student 1 --- 
Enter Roll Number: 1 
Enter name: Ram Patil 
Enter Division: A 
Enter number of subjects: 3 
Enter marks of subject 1: 78 
Enter marks of subject 2: 85 
Enter marks of subject 3: 90 
Roll Number : 1 
Name: Rahul Patil 
Division: A 
Total Marks : 253 
Percentage : 84.3333% --- Student 2 --- 
Enter Roll Number: 2 
Enter name: pihu Kulkarni 
Enter Division: B 
Enter number of subjects: 3 
Enter marks of subject 1: 65 
Enter marks of subject 2: 72 
Enter marks of subject 3: 80 
Roll Number : 2 
Name: Sneha Kulkarni 
Division: B 
Total Marks : 217 
Percentage : 72.3333%


**Experiment – 3: **

Program Code: 
#include <iostream> // Header file for input and output operations 
using namespace std; // Allows use of standard library names without std:: 
// Class definition 
class Patient 
{ 
private: // Private access specifier (data security) 
int patientId; // Stores patient ID 
string patientName;// Stores patient name 
f
loat billAmount; // Stores billing amount 
string appointmentDate; // Stores appointment date 
public: // Public access specifier 
// Default Constructor 
Patient() 
{ 
patientId = 0; // Initialize patient ID 
patientName = "Not Assigned"; // Initialize patient name 
billAmount = 0.0; // Initialize bill amount 
appointmentDate = "Not Fixed"; // Initialize appointment date 
} 
// Parameterized Constructor 
Patient(int id, string name, float bill, string date) 
{ 
patientId = id; // Assign value to patient ID 
patientName = name; // Assign value to patient name 
billAmount = bill; // Assign value to bill amount 
appointmentDate = date;// Assign value to appointment date 
} 
// Copy Constructor 
Patient(Patient &p) 
{ 
patientId = p.patientId; // Copy patient ID 
patientName = p.patientName; // Copy patient name 
billAmount = p.billAmount; // Copy bill amount 
appointmentDate = p.appointmentDate;// Copy appointment date 
} 
// Member function to display patient details 
void display() 
{ 
cout << "\nPatient ID : " << patientId; // Display patient ID 
cout << "\nPatient Name : " << patientName; // Display patient name 
cout << "\nBilling Amount : Rs. " << billAmount; // Display billing amount 
cout << "\nAppointment Date : " << appointmentDate; // Display appointment date 
cout << endl; // New line 
} 
}; 
// Main function 
int main() 
{ 
// Create object using default constructor 
Patient p1; 
cout << "\n--- Default Constructor ---"; 
p1.display(); // Call display function 
// Create object using parameterized constructor 
Patient p2(101, "Rahul Patil", 3500.50, "15-02-2026"); 
cout << "\n--- Parameterized Constructor ---"; 
p2.display(); // Call display function 
// Create object using copy constructor 
Patient p3 = p2; 
cout << "\n--- Copy Constructor ---"; 
p3.display(); // Call display function 
return 0; // End of program 
} 

Output: --- Default Constructor --- 
Patient ID : 0 
Patient Name : Not Assigned 
Billing Amount : Rs. 0 
Appointment Date : Not Fixed --- Parameterized Constructor --- 
Patient ID : 101 
Patient Name : Rahul Patil 
Billing Amount : Rs. 3500.5 
Appointment Date : 15-02-2026 --- Copy Constructor --- 
Patient ID : 101 
Patient Name : Rahul Patil 
Billing Amount : Rs. 3500.5 
Appointment Date : 15-02-2026


**Experiment – 4: **
Program Code : 
#include <iostream> // Header file for input and output 
using namespace std; 
// Class definition 
class Calculator 
{ 
private: 
f
loat a, b; // Data members to store two numbers 
public: 
// Function to accept values 
void getData(float x, float y) 
{ 
a = x; // Assign first number 
b = y; // Assign second number 
} 
// Inline function for addition 
inline float add() 
{ 
return a + b; 
} 
// Inline function for subtraction 
inline float subtract() 
{ 
return a - b; 
} 
// Inline function for multiplication 
inline float multiply() 
{ 
return a * b; 
} 
// Inline function for division 
inline float divide() 
{ 
return a / b; 
} 
}; 
// Main function 
int main() 
{ 
Calculator calc; // Create object of Calculator class 
f
loat x, y; 
// Accept input from user 
cout << "Enter two numbers: "; 
cin >> x >> y; 
// Pass values to object 
calc.getData(x, y); 
// Display results 
cout << "\nAddition = " << calc.add(); 
cout << "\nSubtraction = " << calc.subtract(); 
cout << "\nMultiplication = " << calc.multiply(); 
cout << "\nDivision = " << calc.divide(); 
return 0; // End of program 
} 

Output : 
Enter two numbers: 20 10 
Addition = 30 
Subtraction = 10 
Multiplication = 200 
Division = 2


**Experiment – 5: **

Program: Static Data Member & Static Member Function 
Code : 
#include <iostream> // Header file for input and output 
using namespace std; 
// Class definition 
class Student 
{ 
private: 
static int count; // Static data member (common for all objects) 
public: 
// Constructor 
Student() 
{ 
count++; // Increment count whenever object is created 
} 
// Static member function 
static void showCount() 
{ 
cout << "Total number of students: " << count << endl; 
// Static function can access only static data members 
} 
}; 
// Initialization of static data member 
int Student::count = 0; 
// Main function 
int main() 
{ 
Student s1; // Create first object 
Student s2; // Create second object 
Student s3; // Create third object 
// Call static member function using class name 
Student::showCount(); 
return 0; // End of program 
} 

Output: 
Total number of students: 3


**Experiment – 6: **

Program Code : 
Program: Access Private Members Using Friend Function 
#include <iostream> // Header file for input and output 
using namespace std; 
// Class definition 
class Sample 
{ 
private: 
int a, b; // Private data members 
public: 
// Constructor to initialize values 
Sample(int x, int y) 
{ 
a = x; // Assign value to a 
b = y; // Assign value to b 
} 
// Friend function declaration 
friend void showData(Sample s); 
}; 
// Friend function definition 
void showData(Sample s) 
{ 
// Accessing private members of class 
cout << "Value of a = " << s.a << endl; 
cout << "Value of b = " << s.b << endl; 
cout << "Sum = " << (s.a + s.b) << endl; 
} 
// Main function 
int main() 
{ 
// Create object of Sample class 
Sample obj(10, 20); 
// Call friend function 
showData(obj); 
return 0; // End of program 
} 

OUTPUT 
Value of a = 10 
Value of b = 20 
Sum = 30


**Experiment – 7: **

Program Code : 
Program: Complex Number Class with Operator Overloading 
#include <iostream> 
using namespace std; 
// Class definition for Complex numbers 
class Complex 
{ 
private: 
f
loat real; // Real part 
f
loat imag; // Imaginary part 
public: 
// Default constructor 
Complex() 
{ 
real = 0; 
imag = 0; 
} 
// Parameterized constructor 
Complex(float r, float i) 
{ 
real = r; 
imag = i; 
} 
// Operator overloading for addition 
Complex operator+(Complex c) 
{ 
Complex temp; 
temp.real = real + c.real; // Add real parts 
temp.imag = imag + c.imag; // Add imaginary parts 
return temp; 
} 
// Operator overloading for multiplication 
Complex operator*(Complex c) 
{ 
Complex temp; 
// (a+bi)(c+di) = (ac - bd) + (ad + bc)i 
temp.real = real * c.real - imag * c.imag; 
temp.imag = real * c.imag + imag * c.real; 
return temp; 
} 
// Friend function to overload >> for input 
friend istream& operator>>(istream &in, Complex &c) 
{ 
cout << "Enter real part: "; 
in >> c.real; 
cout << "Enter imaginary part: "; 
in >> c.imag; 
return in; 
} 
// Friend function to overload << for output 
friend ostream& operator<<(ostream &out, Complex c) 
{ 
out << c.real; 
if (c.imag >= 0) 
out << " + " << c.imag << "i"; 
else 
out << " - " << -c.imag << "i"; 
return out; 
} 
}; 
// Main function 
int main() 
{ 
Complex c1, c2, sum, product; 
cout << "--- Input first complex number ---\n"; 
cin >> c1; 
cout << "\n--- Input second complex number ---\n"; 
cin >> c2; 
// Perform addition 
sum = c1 + c2; 
// Perform multiplication 
product = c1 * c2; 
// Display results 
cout << "\nSum of complex numbers: " << sum << endl; 
cout << "Product of complex numbers: " << product << endl; 
return 0; 
} 

OUTPUT --- Input first complex number --- 
Enter real part: 3 
Enter imaginary part: 2 --- Input second complex number --- 
Enter real part: 1 
Enter imaginary part: 4 
Sum of complex numbers: 4 + 6i 
Product of complex numbers: -5 + 14i --- Input first complex number --- 
Enter real part: 3 
Enter imaginary part: 2 --- Input second complex number --- 
Enter real part: 1 
Enter imaginary part: 4 
Sum of complex numbers: 4 + 6i 
Product of complex numbers: -5 + 14i

**Experiment – 8: **

Program Code : 
Program: Student Information Using Inheritance 
#include <iostream> 
#include <string> 
using namespace std; 
// Base class: Student 
class Student 
{ 
protected: 
int rollNo; // Roll number of student 
string name; // Name of student 
public: 
// Function to accept student details 
void getStudentInfo() 
{ 
cout << "Enter Roll Number: "; 
cin >> rollNo; 
cin.ignore(); // Clear input buffer 
cout << "Enter Name: "; 
getline(cin, name); 
} 
}; 
// Derived class: Marks (inherits Student) 
class Marks : public Student 
{ 
private: 
f
loat marks[5]; // Marks in 5 subjects 
f
loat total; // Total marks 
public: 
// Function to accept marks 
void getMarks() 
{ 
total = 0; 
for (int i = 0; i < 5; i++) 
{ 
cout << "Enter marks of subject " << i + 1 << ": "; 
cin >> marks[i]; 
total += marks[i]; 
} 
} 
// Function to display student details and marks 
void display() 
{ 
cout << "\n--- Student Information ---\n"; 
cout << "Roll Number: " << rollNo << endl; 
cout << "Name : " << name << endl; 
cout << "Marks : "; 
for (int i = 0; i < 5; i++) 
{ 
cout << marks[i] << " "; 
} 
cout << "\nTotal Marks: " << total << endl; 
cout << "Percentage : " << (total / 5) << "%\n"; 
} 
}; 
// Main function 
int main() 
{ 
Marks student; // Create object of derived class 
// Accept student info 
student.getStudentInfo(); 
// Accept marks 
student.getMarks(); 
// Display student info and marks 
student.display(); 
return 0; 
} 
OUTPUT : 
Enter Roll Number: 101 
Enter Name: Rahul Patil 
Enter marks of subject 1: 78 
Enter marks of subject 2: 82 
Enter marks of subject 3: 90 
Enter marks of subject 4: 75 
Enter marks of subject 5: 85 --- Student Information --- 
Roll Number: 101 
Name : Rahul Patil 
Marks : 78 82 90 75 85 
Total Marks: 410 
Percentage : 82% 
Program: Employee Info with Multilevel & Hierarchical Inheritance 

Program Code : 
#include <iostream> 
#include <string> 
using namespace std; 
// Base class: Employee 
class Employee 
{ 
protected: 
int empId; 
string empName; 
f
loat basicSalary; 
public: 
void getEmployeeInfo() 
{ 
cout << "Enter Employee ID: "; 
cin >> empId; 
cin.ignore(); 
cout << "Enter Employee Name: "; 
getline(cin, empName); 
cout << "Enter Basic Salary: "; 
cin >> basicSalary; 
} 
}; 
// Derived class (Multilevel): Department 
class Department : public Employee 
{ 
protected: 
string deptName; 
public: 
void getDepartmentInfo() 
{ 
cin.ignore(); 
cout << "Enter Department Name: "; 
getline(cin, deptName); 
} 
}; 
// Derived class (Multilevel): PF (from Department) 
class PF : public Department 
{ 
protected: 
f
loat pfAmount; 
public: 
void calculatePF() 
{ 
pfAmount = basicSalary * 0.12; // 12% of basic salary 
} 
void displayPFInfo() 
{ 
cout << "\n--- Employee Details (Multilevel Inheritance) ---\n"; 
cout << "Employee ID : " << empId << endl; 
cout << "Employee Name : " << empName << endl; 
cout << "Department : " << deptName << endl; 
cout << "Basic Salary : " << basicSalary << endl; 
cout << "PF Amount (12%) : " << pfAmount << endl; 
} 
}; 
// Another Derived class (Hierarchical) from Employee 
class Project : public Employee 
{ 
protected: 
string projectName; 
public: 
void getProjectInfo() 
{ 
cin.ignore(); 
cout << "Enter Project Name: "; 
getline(cin, projectName); 
} 
void displayProjectInfo() 
{ 
cout << "\n--- Employee Project Info (Hierarchical Inheritance) ---\n"; 
cout << "Employee ID : " << empId << endl; 
cout << "Employee Name : " << empName << endl; 
cout << "Project Name : " << projectName << endl; 
} 
}; 
// Main function 
int main() 
{ 
// Object for multilevel inheritance 
PF emp1; 
cout << "--- Enter Employee Info for PF ---\n"; 
emp1.getEmployeeInfo(); 
emp1.getDepartmentInfo(); 
emp1.calculatePF(); 
emp1.displayPFInfo(); 
// Object for hierarchical inheritance 
Project emp2; 
cout << "\n--- Enter Employee Info for Project ---\n"; 
emp2.getEmployeeInfo(); 
emp2.getProjectInfo(); 
emp2.displayProjectInfo(); 
return 0; 
} 
OUTPUT --- Enter Employee Info for PF --- 
Enter Employee ID: 101 
Enter Employee Name: Rahul Patil 
Enter Basic Salary: 50000 
Enter Department Name: HR --- Employee Details (Multilevel Inheritance) --- 
Employee ID : 101 
Employee Name : Rahul Patil 
Department : HR 
Basic Salary : 50000 
PF Amount (12%) : 6000 --- Enter Employee Info for Project --- 
Enter Employee ID: 102 
Enter Employee Name: Sneha Kulkarni 
Enter Basic Salary: 60000 
Enter Project Name: Project Phoenix --- Employee Project Info (Hierarchical Inheritance) --- 
Employee ID : 102 
Employee Name : Sneha Kulkarni 
Project Name : Project Phoenix


**Experiment – 9: **
Program Code : 
Program: Abstract Class Example 
#include <iostream> 
#include <string> 
using namespace std; 
// Abstract class 
class Shape 
{ 
public: 
// Pure virtual function (makes this class abstract) 
virtual void area() = 0; 
// Another pure virtual function 
virtual void perimeter() = 0; 
}; 
// Derived class: Rectangle 
class Rectangle : public Shape 
{ 
private: 
f
loat length, width; 
public: 
// Function to accept rectangle dimensions 
void getData() 
{ 
cout << "Enter length of rectangle: "; 
cin >> length; 
cout << "Enter width of rectangle: "; 
cin >> width; 
} 
// Override pure virtual function to calculate area 
void area() 
{ 
cout << "Area of rectangle = " << length * width << endl; 
} 
// Override pure virtual function to calculate perimeter 
void perimeter() 
{ 
cout << "Perimeter of rectangle = " << 2 * (length + width) << endl; 
} 
}; 
// Derived class: Circle 
class Circle : public Shape 
{ 
private: 
f
loat radius; 
public: 
void getData() 
{ 
cout << "Enter radius of circle: "; 
cin >> radius; 
} 
void area() 
{ 
cout << "Area of circle = " << 3.1416 * radius * radius << endl; 
} 
void perimeter() 
{ 
cout << "Perimeter (Circumference) of circle = " << 2 * 3.1416 * radius << endl; 
} 
}; 
// Main function 
int main() 
{ 
Rectangle rect; 
Circle circ; 
cout << "--- Rectangle ---\n"; 
rect.getData(); 
rect.area(); 
rect.perimeter(); 
cout << "\n--- Circle ---\n"; 
circ.getData(); 
circ.area(); 
circ.perimeter(); 
return 0; 
} 
OUTPUT --- Rectangle --- 
Enter length of rectangle: 10 
Enter width of rectangle: 5 
Area of rectangle = 50 
Perimeter of rectangle = 30 --- Circle --- 
Enter radius of circle: 7 
Area of circle = 153.938 
Perimeter (Circumference) of circle = 43.9824


**Experiment – 10: **

Program Code : 
Program Demonstrating Polymorphism 
#include <iostream> 
using namespace std; 
// ----------------- Compile-Time Polymorphism (Function Overloading) ----------------- 
class Calculator 
{ 
public: 
// Function to add two integers 
int add(int a, int b) 
{ 
return a + b; 
} 
// Function to add three integers (overloading) 
int add(int a, int b, int c) 
{ 
return a + b + c; 
} 
// Function to add two floating-point numbers (overloading) 
f
loat add(float a, float b) 
{ 
return a + b; 
} 
}; 
// ----------------- Run-Time Polymorphism (Function Overriding) ----------------- 
class Shape 
{ 
public: 
// Virtual function for area 
virtual void area() 
{ 
cout << "Area of generic shape" << endl; 
} 
}; 
class Rectangle : public Shape 
{ 
private: 
f
loat length, width; 
public: 
Rectangle(float l, float w) 
{ 
length = l; 
width = w; 
} 
// Overriding the area function 
void area() override 
{ 
cout << "Area of rectangle = " << length * width << endl; 
} 
}; 
class Circle : public Shape 
{ 
private: 
f
loat radius; 
public: 
Circle(float r) 
{ 
radius = r; 
} 
// Overriding the area function 
void area() override 
{ 
cout << "Area of circle = " << 3.1416 * radius * radius << endl; 
} 
}; 
// ----------------- Main Function ----------------- 
int main() 
{ 
// Compile-time polymorphism demonstration 
Calculator calc; 
cout << "--- Compile-Time Polymorphism (Function Overloading) ---\n"; 
cout << "Sum of 2 integers: " << calc.add(10, 20) << endl; 
cout << "Sum of 3 integers: " << calc.add(5, 10, 15) << endl; 
cout << "Sum of 2 floats: " << calc.add(2.5f, 3.5f) << endl; 
// Run-time polymorphism demonstration 
Shape *s1, *s2; 
Rectangle rect(10, 5); 
Circle circ(7); 
s1 = &rect; // Base class pointer pointing to derived class object 
s2 = &circ; 
cout << "\n--- Run-Time Polymorphism (Function Overriding) ---\n"; 
s1->area(); // Calls Rectangle's area() 
s2->area(); // Calls Circle's area() 
return 0; 
} 
OUTPUT --- Compile-Time Polymorphism (Function Overloading) --- 
Sum of 2 integers: 30 
Sum of 3 integers: 30 
Sum of 2 floats: 6 --- Run-Time Polymorphism (Function Overriding) --- 
Area of rectangle = 50 
Area of circle = 153.938


**Experiment – 11: **

Program Code: 
Program: Operator Overloading & Function Overriding 
#include <iostream> 
using namespace std; 
// ----------------- Base class for Function Overriding ----------------- 
class Shape 
{ 
public: 
// Virtual function to display shape type 
virtual void display() 
{ 
cout << "This is a generic shape." << endl; 
} 
}; 
// Derived class: Rectangle 
class Rectangle : public Shape 
{ 
private: 
f
loat length, width; 
public: 
Rectangle(float l, float w) 
{ 
length = l; 
width = w; 
} 
// Overriding the display function 
void display() override 
{ 
cout << "This is a rectangle with length " << length 
<< " and width " << width << "." << endl; 
} 
// Function to get area 
f
loat area() 
{ 
return length * width; 
} 
// Operator overloading for + (adding areas of two rectangles) 
f
loat operator+(Rectangle r) 
{ 
return this->area() + r.area(); 
} 
}; 
// ----------------- Main function ----------------- 
int main() 
{ 
// Operator Overloading demonstration 
Rectangle rect1(5, 10); 
Rectangle rect2(3, 4); 
f
loat totalArea = rect1 + rect2; // Calls overloaded + operator 
cout << "--- Operator Overloading ---" << endl; 
cout << "Area of rect1: " << rect1.area() << endl; 
cout << "Area of rect2: " << rect2.area() << endl; 
cout << "Total area (rect1 + rect2) using overloaded +: " << totalArea << endl; 
// Function Overriding demonstration 
Shape *s; 
Rectangle rect3(7, 2); 
s = &rect3; // Base class pointer pointing to derived class object 
cout << "\n--- Function Overriding ---" << endl; 
s->display(); // Calls Rectangle's display() due to runtime polymorphism 
return 0; 
} 
OUTPUT --- Operator Overloading --- 
Area of rect1: 50 
Area of rect2: 12 
Total area (rect1 + rect2) using overloaded +: 62 --- Function Overriding --- 
This is a rectangle with length 7 and width 2.

