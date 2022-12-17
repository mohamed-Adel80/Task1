using system;

namespace task;

public class person
{
    public String Name;

    public int age;

    Public person(string Name , int age)
    {
        Name = name;
        Age = age;
    }

    public abstract void print();

}

public class student : person
{
    public int year;

    public float gpa;

    public student(string name, int age, int year, float gpa)
        :base(name, age)
        {
            year = year;
            gpa = gpa;
        }

    public override void print()
    {
        console.WriteLine
        ("my name is {name}, my age is {Age}, and gpa is {Gpa}");
    }
}


public class staff : person
{
    double salary;

    int joinyear;

    public staff(string name, int age, double salary, int jionyear) : base(name)
    {
        salary = salary;
        joinyear = joinyear;
    }

    public override void print()
    {
        Console.WriteLine
        ("my name is {name}, my age is {age}, and my salary is {salary}");
    }
}

public class database
{
    private int _currentIndex;

    public person[] people = new.person[50];

    public void AddStudent(student student)
    {
        people[_currentIndex++] = student;
    }

    public void AddStaff(staff staff)
    {
        people[_currentIndex++] = staff;

    }

    public void printAll()
    {
        foreach (var item in people)
        {
            item?.print();

        }
    }
}

public class program
{
    private static void Main()
    {
        var database = new database();

        while(true)
        {
            console.WriteLine("1");
            
            console.Write("option: ");

            var option = convert.ToInt32(console.ReadLine);

            switch(option)
            {
                case 1:

                    console.Write("name: ");

                    var name = console.ReadLine();

                    console.Write("age: ");

                    var age = convert.ToInt32(console.ReadLine());

                    console.Write("year: ");

                    var year = convert.ToInt32(console.ReadLine());

                    console.Write("gpa: ");

                    var gpa = convert.ToSingle(console.ReadLine());

                    var student = new student(name, age, year, gpa);

                    database.AddStudent(student);

                    break;
                case 2:

                    console.Write("name: ");

                    var name2 = console.ReadLine();

                    console.Write("age: ");

                    var age2 = convert.ToInt32(console.ReadLine());

                    console.Write("salary: ");

                    var salary = convert.ToDouble(console.ReadLine());

                    console.Write("join year: ");

                    var joinyear = convert.ToInt32(console.ReadLine());

                    var staff = new staff(name2, age2, salary, joinyear);

                    database.AddStaff(staff);
                    
                    break;
                
                case 3:
                    console.Write("name: ");

                    var name3 = console.ReadLine();

                    console.Write("age: ");

                    var age3 = convert.ToInt32(console.ReadLine());


                    var person = new person(name3, age3);

                    database.AddPerson(person);

                    break;
                
                case 4:

                    database printAll();

                    break;

                default:

                    return;

            }



        }
    }
}



