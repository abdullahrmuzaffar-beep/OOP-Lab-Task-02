# OOP-Lab-Task-02

Lab Task 2: University System using OOP principles
 
class Person
{
    protected String name;
    protected int age;
    
    static String universityName = "NUML Lahore";
 
    public Person(String name, int age)
    {
        this.name = name;
        this.age = age;
    }
 
    public static void showUniversityInfo()
    {
        System.out.println("University: " + universityName);
    }
 
    public void displayInfo()
    {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}
 
class Teacher extends Person 
{
    private String subject;
    private double salary;
 
    public Teacher(String name, int age, String subject, double salary)
    {
        super(name, age);
        this.subject = subject;
        this.salary = salary;
    }
 
    public Teacher(String name, String subject)
    {
        super(name, 0);
        this.subject = subject;
        this.salary = 0.0;
    }
 
    public void displayInfo()
    {
        System.out.println("--- Teacher Info ---");
        super.displayInfo();
        System.out.println("Subject: " + subject);
        System.out.println("Salary: " + salary);
    }
}
 
class Student extends Person 
{
    private int rollNo;
    private double marks;
 
    public Student(String name, int age, int rollNo, double marks)
    {
        super(name, age);
        this.rollNo = rollNo;
        this.marks = marks;
    }
 
    public Student(String name, int rollNo)
    {
        super(name, 0);
        this.rollNo = rollNo;
        this.marks = 0.0;
    }
 
    public void displayInfo() 
    {
        System.out.println("--- Student Info ---");
        super.displayInfo();
        System.out.println("Roll No: " + rollNo);
        System.out.println("Marks: " + marks);
    }
}
 
public class Main
{
    public static void main(String[] args)
    {
        Person.showUniversityInfo();
        System.out.println();
 
         Student s1 = new Student("Ali", 19, 101, 85.5);
        Student s2 = new Student("Sara", 102);
        Teacher t1 = new Teacher("Dr. Ahmed", 40, "OOP", 150000);
        Teacher t2 = new Teacher("Ms. Fatima", "Data Structures");

        s1.displayInfo();
        System.out.println();
        s2.displayInfo();
        System.out.println();
        t1.displayInfo();
        System.out.println();
        t2.displayInfo();

        System.out.println();
        Person.universityName = "NUML University";
        Person.showUniversityInfo();
    }
}
