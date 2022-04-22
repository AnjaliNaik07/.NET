using System;<br>
namespace Exercises<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n--------AMICABLE NUMBERS-----------\n");<br>
            Console.Write("\nEnter the first number: ");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the second number: ");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {<br>
                Console.WriteLine("\nThe numbers {0} and {1} are amiciable.", num1, num2);<br>
            }<br>
            else<br>            
            {<br>
                Console.WriteLine("\nThe numbers {0} and {1} are not amiciable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>
<br>




using System;<br>
namespace Exercises<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[]args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.Write("\n enter the number of lines:  ");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for(int i=1;i<=number;i++)<br>
            {<br>
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>
                for(int j=0;j<i;j++)<br>
                {<br>
                    Console.Write(digit + " ");<br>
                    digit = (digit ==1) ? 0 : 1;<br>
                }<br>
                Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/99865210/154622332-1ade41a6-0523-46f1-a3d3-45052376946c.png)
<br>
<br>




using System;<br>
using System.IO;<br>
namespace Exercises<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("Enter the first file path:");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("Enter the second file path:");<br>
            file2 = Console.ReadLine();<br>
            if (!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("First file does not exist!");<br>
            }<br>
            else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("Second file does not exist!");<br>
            }<br>
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both files contain the same content");<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("Contents of files are not same");<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/99865210/154624503-3ae20be7-a6bf-4831-a46c-a4878f4ad353.png)<br>
<br>
![image](https://user-images.githubusercontent.com/99865210/154624664-94d92055-d890-4b0c-9c8b-450055d5a0cb.png)<br>
<br>
<br>

using System;<br>
using System.IO;<br>
namespace Exercises<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n --------------- MENU --------------- \n");<br>
                Console.WriteLine("\n 1.Create a File ");<br>
                Console.WriteLine("\n 2.Existence of the File ");<br>
                Console.WriteLine("\n 3.Read the contents of the File ");<br>
                Console.WriteLine("\n 4.Exit ");<br>
                Console.Write("\n Enter your choice : ");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\n Enter the file name to create: ");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\n Write the Contents to the File: \n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is Created...");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\n Enter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exists...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exist in the current directory!");<br>
                            }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine(" Here is the content of the file : ");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>                        
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
                }<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>

![image](https://user-images.githubusercontent.com/99865210/154628287-5d8ec52e-dc30-418b-b311-a73809d0d881.png)<br>
![image](https://user-images.githubusercontent.com/99865210/154628412-862c427d-9550-4074-ac40-876956a23bcd.png)<br>
<br>
<br>




using System;<br>
namespace Exercises<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
 Fraction[] a = {<br>
new Fraction(5,2),<br>
new Fraction(29,6),<br>
new Fraction(4,5),<br>
new Fraction(10,8),<br>
new Fraction(34,7)<br>
};<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying Fractions: ");<br>
        foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
                }<br>
            }<br>
}<br>
<br>
<br>

   ![image](https://user-images.githubusercontent.com/99865210/154630067-3c4885a3-d2ee-4eab-b6f1-88ed5209db4a.png)<br>
   <br>

   
   using System;   <br>
using System.Diagonostics;     <br>                                                   
namespace Exercises   <br>
{   <br>
    class BenchmarkAllocation   <br>
    {   <br>   
        const int _max = 100000;   <br>   
        static void Main(string[] args)   <br>   
        {   <br>
            var Arr2D = new int[100, 100];   <br>   
            var ArrJagged = new int[100][];   <br>
            for (int i = 0; i < 100; i++)   <br>
            {   <br>
                ArrJagged[i] = new int[100];   <br>
            }   <br>
            var Stopwatch2D = Stopwatch.StartNew();   <br>
            for (int i = 0; i < _max; i++)   <br>
            {   <br>
                for (int j = 0; j < 100; j++)   <br>
                {   <br>
                    for (int k = 0; k < 100; k++)   <br>
                    {   <br>
                        Arr2D[j, k] = k;   <br>
                    }   <br>
                }   <br>
            }   <br>
            Stopwatch2D.Stop();   <br>
            var StopwatchJagged = Stopwatch.StartNew();   <br>
            for (int i = 0; i < _max; i++)   <br>
            {   <br>
                for (int j = 0; j < 100; j++)   <br>
                {   <br>
                    for (int k = 0; k < 100; k++)   <br>
                    {   <br>
                        ArrJagged[j][k] = k;   <br>
                    }   <br>
                }   <br>
            }   <br>
            StopwatchJagged.Stop();   <br>
 Console.Write("\n Time taken for allocation in case of 2D array: ");   <br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + " milliseconds");   <br>
            Console.Write("\n Time taken for allocation in case of Jagged array: ");   <br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + " milliseconds");   <br>
        }   <br>
    }   <br>
}   <br>
      <br>
   ![image](https://user-images.githubusercontent.com/99865210/154632729-4889eed0-387a-4963-9278-a9d8229ab2b8.png)<br>
   <br>



using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>
<br>
<br>


![image](https://user-images.githubusercontent.com/99865210/154633769-3d482726-cb11-470d-8e41-d1a81d2a727a.png)<br>
<br><br>




using System;    <br>
namespace Exercises<br>
{<br>
class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputString;<br>
            Console.WriteLine("\n----------- Frequency of word 'is' ----------");<br>
            Console.Write("\n Enter the input string: ");<br>
            inputString = Console.ReadLine();<br>
            char[] separator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputString.ToLower();<br>
            String[] outcomes = testString.Split(separator);<br>
            foreach (String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
                    }<br>
            Console.WriteLine("\n Number of 'is' in '" + inputString + "' is: " + count);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/99865210/154635121-65d2ddf9-f026-4d6e-b44b-92616e638d57.png)<br>
<br>



using System;<br>
namespace Exercises<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>
        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNo = ++startNum;<br>
        }<br>
        public static void Main(string[] args)<br>
        {<br>
            for (int i = 0; i < 100; i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("Student {0} : {1}", i + 1, Student.regNo);<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/99865210/154635689-d3232bf9-fc29-4b7b-b851-6ad0e2ad5728.png)<br>
<br>






using System;<br>
namespace Exercises<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number: ");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}: {1}", InputNum,<br>
            Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\nGray Code equivalent of {0}: {1}", InputNum,<br>
            Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
}<br>
namespace Exercises<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number: ");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}: {1}", InputNum,<br>
            Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\nGray Code equivalent of {0}: {1}", InputNum,<br>
            Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
}<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/99865210/154636573-89d3d748-a0cd-4644-9f42-8c5294155fa5.png)<br>
<br>



using System;<br>
namespace Exercises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n-------- PERSONAL DETAILS --------\n");<br>
            Console.WriteLine("Name : " + name);<br>
            Console.WriteLine("Age : " + age);<br>
            Console.WriteLine("Gender : " + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester)<br>
        : base(name, age, gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>
 Console.WriteLine("Register Number : " + regNo);<br>
            Console.WriteLine("Course : " + course);<br>
            Console.WriteLine("Semester : " + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester,<br>
        int[] marks) : base(name, age, gender, regNo, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50)<br>
                grade = "Second Class";<br>
else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- MARKS DETAILS --------\n");<br>
            Console.Write("Marks in 5 subjects: ");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total : " + total);<br>
            Console.WriteLine("Average : " + average);<br>
            Console.WriteLine("Grade : " + grade);<br>
        }<br>
    }<br>
 class MultiLevel<br>
    {<br><br>
        public static void Main(string[] args)
        {<br>
            MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5,<br>
            new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
        }<br>
    }<br>
<br>
<br>

![image](https://user-images.githubusercontent.com/99865210/154638091-5a00ca9b-55ed-46c7-8e55-7fea6bc38ef6.png)<br>
<br>




.NET TECHNOLOGY  (C#)LAB PROGRAMS  LIST

*PROGRAMS AND OUTPUT*

01. Write a c# program to print fibonacci series without using recursion?

using System;
namespace Exercises
{
public class FibonacciExample
{
public static void Main(string[] args)
{
int n1 = 0, n2 = 1, n3, i, number;
Console.Write("Enter the number of elements: ");
number = int.Parse(Console.ReadLine());
Console.Write(n1 + " " + n2 + " ");
for (i = 2; i < number; ++i)

{
n3 = n1 + n2;
Console.Write(n3 + " ");
n1 = n2;
n2 = n3;
}
}
}
}


 

02.Write a C# program to check the prime numbers?

using System;
namespace Exercises
{
public class PrimeNumberExample
{
public static void Main(string[] args)
{
int n, i, m = 0, flag = 0;
Console.Write("Enter the Number to check Prime: ");
n = int.Parse(Console.ReadLine());
m = n / 2;
for (i = 2; i <= m; i++)
{
if (n % i == 0)
{
Console.Write("Number is not Prime.");
flag = 1;
break;
}
}
if (flag == 0)
Console.Write("Number is Prime.");
}
}
}

   


03.Write a c# program to check palindrome number?

using System;
namespace exercises
{
public class PalindromeExample
{
public static void Main(string[] args)
{
int n, r, sum = 0, temp;
Console.Write("Enter the Number: ");
n = int.Parse(Console.ReadLine());
temp = n;
while (n > 0)
{
r = n % 10;
sum = (sum * 10) + r;
n = n / 10;
}
if (temp == sum)
Console.Write("Number is Palindrome.");
else
Console.Write("Number is not Palindrome");
}
}
}

   


04.Write a c# program to print factorial of a number?

using System;
namespace Exercises
{
public class FactorialExample
{
public static void Main(string[] args)
{
int i, fact = 1, number;
Console.Write("Enter any Number: ");
number = int.Parse(Console.ReadLine());
for (i = 1; i <= number; i++)
{
fact = fact * i;
}
Console.Write("Factorial of " + number + " is: " + fact);
}
}
}


 








05.Write a c# program to check the armstrong number?

using System;
namespace Exercises
{
public class ArmstrongExample
{
public static void Main(string[] args)
{
int n, r, sum = 0, temp;
Console.Write("Enter the Number= ");
n = int.Parse(Console.ReadLine());
temp = n;
while (n > 0)
{
r = n % 10;
sum = sum + (r * r * r);
n = n / 10;
}
if (temp == sum)
Console.Write("Armstrong Number.");
else
Console.Write("Not Armstrong Number.");
}
}}

   



06. Write a c# program to print sum of digits?

using System;
namespace Exercises
{
public class SumExample
{
public static void Main(string[] args)
{
int n, sum = 0, m;
Console.Write("Enter a number: ");
n = int.Parse(Console.ReadLine());
while (n > 0)
{
m = n % 10;
sum = sum + m;
n = n / 10;
}
Console.Write("Sum is= " + sum);
}
}
}
 









07.Write a c# program to reverse a given number?

using System;
namespace Exercises
{
public class ReverseExample
{
public static void Main(string[] args)
{
int n, reverse = 0, rem;
Console.Write("Enter a number: ");
n = int.Parse(Console.ReadLine());
while (n != 0)
{
rem = n % 10;
reverse = reverse * 10 + rem;
n /= 10;
}
Console.Write("Reversed Number: " + reverse);
}
}
}

 







08.C# program to print Binary Triangle?

using System;
namespace Exercises
{
class BinaryTriangle
{
static void Main(string[] args)
{
int number, digit = 1;
Console.Write("\nEnter the number of lines: ");
number = Convert.ToInt32(Console.ReadLine());
for (int i = 1; i <= number; i++)
{
for (int space = number - i; space > 0; space--)
{
Console.Write(" ");
}
for (int j = 0; j < i; j++)
{
Console.Write(digit + " ");
digit = (digit == 1) ? 0 : 1;
}
Console.Write("\n");
}
}
}    
}

    

09.C# program to check whether the entered number is an Amicable number or not?

using System;
namespace Exercises
{
class AmicableNumber
{
static void Main(string[] args)
{
int num1, num2, sum1 = 0, sum2 = 0;
Console.WriteLine("\n--------AMICABLE NUMBERS-----------\n");
Console.Write("\nEnter the first number: ");
num1 = Convert.ToInt32(Console.ReadLine());
Console.Write("\nEnter the second number: ");
num2 = Convert.ToInt32(Console.ReadLine());
for (int i = 1; i < num1; i++)
{
if (num1 % i == 0)
{
sum1 += i;
}
}
for (int i = 1; i < num2; i++)
{
if (num2 % i == 0)
{
sum2 += i;
}
}
if (sum1 == num2 && sum2 == num1)
{
Console.WriteLine("\nThe numbers {0} and {1} are amiciable.", num1, num2);
}
else
{
Console.WriteLine("\nThe numbers {0} and {1} are not amiciable.", num1, num2);
}
}
}
}



 
 











10.C# program to illustrate Multilevel Inheritance with Virtual methods?

using System;
namespace Exercises
{
class PersonalDetails
{
string name;
int age;
string gender;
public PersonalDetails(string name, int age, string gender)
{
this.name = name;
this.age = age;
this.gender = gender;
}
public virtual void Display()
{
Console.WriteLine("\n-----------PERSONAL DETAILS-----------\n");
Console.WriteLine("Name :" + name);
Console.WriteLine("Age :" + age);
Console.WriteLine("Gender :" + gender);
}
}
class CourseDetails : PersonalDetails
{
int regNo;
string course;
int semester;
public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)
{
this.regNo = regNo;
this.course = course;
this.semester = semester;
}
public override void Display()
{
base.Display();
Console.WriteLine("/n-------------CourseDetails-----------\n");
Console.WriteLine("Register Number:" + regNo);
Console.WriteLine("Course:" + course);
Console.WriteLine("Semester:" + semester);
}
}
class MarksDetails : CourseDetails
{
int[] marks = new int[5];
int total;
float average;
string grade;
int flagFail;
public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)
{
total = 0;
for (int i = 0; i < 5; i++)
{
this.marks[i] = marks[i];
total += marks[i];
if (marks[i] < 35)
{
flagFail = 1;
}
}
Calculate();
}
private void Calculate()
{
average = total / 5;
if (flagFail == 1 || average < 40)
grade = "Fail";
else if (average >= 70)
grade = "Distinction";
else if (average >= 60)
grade = "First class";
else if (average >= 50)
grade = "Second class";
else
grade = "Pass class";
}
public override void Display()
{
base.Display();
Console.WriteLine("\n---------------Marks Details--------------\n");
Console.WriteLine("Marks in 5 subjects:");
for (int i = 0; i < 5; i++)
Console.Write(marks[i] + "");
Console.WriteLine();
Console.WriteLine("Total:" + total);
Console.WriteLine("Average:" + average);
Console.WriteLine("Grade:" + grade);
}
}
class Multilevel
{
public static void Main(string[] args)
{
MarksDetails student1 = new MarksDetails("Abhijith", 22, "Male", 2019001, "MCA", 5, new int[] { 77, 80, 98, 95, 90 });
student1.Display();
}
}
}

 
11.C# program to create a Gray code?

using System;
namespace Exercises
{
class GrayCode
{
static int getGray(int n)
{
return n ^ (n >> 1);
}
static void Main(string[] args)
{
int InputNum, GrayNum;
Console.Write("\nEnter the decimal number:");
InputNum = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("\nBinary equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));
GrayNum = getGray(InputNum);
Console.WriteLine("\nGray code equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum, 2));
}
}
}

 
12.C# program to calculate volume of two boxes and find the resultant volume after addition of 2 boxes by implementing operator overloading?

using System;
namespace Exercises
{
class Box
{
float width;
float height;
float length;
public float Volume
{
get { return width * height * length;}
}
public Box(float width,float height,float length)
{
this.width = width;
this.height = height;
this.length = length;
}
public static float operator+(Box box1,Box box2)
{
return box1.Volume + box2.Volume;
}
public override string ToString()
{
return "box with width" + width + ",height" + height + "and length" + length;
}
}
class Operatoroverloading
{
public static void Main()
{
Box box1 = new Box(10, 20, 30);
Box box2 = new Box(20, 25, 15);
Console.WriteLine("Volume of {0} is:{1}", box1, box1.Volume);
Console.WriteLine("Volume of {0} is:{1}", box2, box2.Volume);
Console.WriteLine("Volume after adding boxes:{0}", box1 + box2);
    }
}}

 
13.C# program to implement principles of delegates?

using System;
namespace Exercises
{
class Delegates
{
delegate string UppercaseDelegate(string input);
static string UppercaseFirst(string input)
{
char[]buffer = input.ToCharArray();
buffer[0] = char.ToUpper(buffer[0]);
return new string(buffer);
}
static string UppercaseLast(string input)
{
char[] buffer = input.ToCharArray();
buffer[buffer.Length - 1] = Char.ToUpper(buffer[buffer.Length - 1]);
return new string(buffer);
}
static string UppercaseAll(string input)
{
return input.ToUpper();
}
static void WriteOutput(string input,UppercaseDelegate del)
{
Console.WriteLine("Input string:{0}", input);
Console.WriteLine("Output string:{0}", del(input));
}
static void Main()
{
WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));
WriteOutput("tom", new UppercaseDelegate(UppercaseLast));
WriteOutput("tom", new UppercaseDelegate(UppercaseAll));
Console.ReadLine();
}
}
}

 
















14.C# program to generate Register Number automatically for 100 students using static constructor?

using System;
namespace Exercises
{
class RegisterNum
{
int regNo;
static int StartNum;
static RegisterNum()
{
StartNum = 20210000;
}
RegisterNum()
{
regNo = ++StartNum;
}
public static void Main(string[] args)
{
for (int i = 0; i < 100; i++)
{
RegisterNum Student = new RegisterNum();
Console.WriteLine("Student {0}:{1}", i + 1, Student.regNo);
}
}
}
}


       












15.C# program to find the frequency of the word "is" in a given sentence?

using System;
namespace Exercises
{
class FrequencyIS
{
static void Main(string[] args)
{
int count = 0;
string inputString;
Console.WriteLine("\n------------Frequency of word 'is'------------");
Console.WriteLine("\n Enter the input string:");
inputString = Console.ReadLine();
char[] seperator = { ',', ' ', '.', '!', '\n' };
string testString = inputString.ToLower();
string[] outcomes = testString.Split(seperator);
foreach(String S in outcomes)
{
Console.WriteLine(S);
if (S == "is")
count++;
}
Console.WriteLine("\n Number of 'is' in" + inputString + "is:" + count);
}
}
}


 

















16.C# program of benchmark 2D,jagged array allocation?

using System;
using System.Diagnostics;
namespace Exercises
{
class BenchmarkAllocation
{
const int max = 100000;
static void Main(string[] args)
{
var Arr2D = new int[100, 100];
var ArrJagged = new int[100][];
for (int i = 0; i < 100; i++)
{
ArrJagged[i] = new int[100];
}
var Stopwatch2D = Stopwatch.StartNew();
for (int i = 0; i<=max;i++)
{
for (int j = 0; j < 100; j++)
{
for (int k = 0; k < 100; k++)
{
Arr2D[j, k] = k;
}
}
}
Stopwatch2D.Stop();
var StopwatchJagged = Stopwatch.StartNew();
for(int i=0;i<=max;i++)
{
for(int j=0;j<100;j++)
{
for(int k=0;k<100;k++)
{
ArrJagged[j][k] = k;
}
}
}
StopwatchJagged.Stop(); Console.WriteLine("\n Time taken for allocation in case of 2D array:");
Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds");
Console.WriteLine("\n Time taken for the allocation in case of Jagged array:");
Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");
    }
}
}


 












17.C# program to find the sum of the values on Diagonal of the matrix?

using System;
namespace Exercises
{
class SumOfDiagonals
{
static void Main(string[] args)
{
int MaxRow, MaxCol, Sum = 0;
int[,] Matrix;
Console.WriteLine("\n--------------SUM OF DIAGONAL OF A MATRIX--------------\n");
Console.WriteLine("\n Enter the number of rows:");
MaxRow = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("\n Enter the number of columns:");
MaxCol = Convert.ToInt32(Console.ReadLine());
if (MaxRow != MaxCol)
{
Console.WriteLine("\n the dimension entered are not of square Matrix");
Console.WriteLine("\n exiting the Program-----");
return;
}
Matrix = new int[MaxRow, MaxCol];
for (int i = 0; i < MaxRow; i++)
{
for (int j = 0; j < MaxCol; j++)
{
Console.Write("\n enter the {0},{1} the element of the matrix:", (i + 1), (j + 1));
Matrix[i, j] = Convert.ToInt32(Console.ReadLine());
}
}
Console.WriteLine("\n the entered Matrix is:");
for (int i = 0; i < MaxRow; i++)
{
for (int j = 0; j < MaxCol; j++)
{
Console.Write(" " + Matrix[i, j]);
if (i == j)
{
Sum += Matrix[i, j];
}
}
Console.WriteLine();
}
Console.WriteLine("\n the sum of diagonal is" + Sum);
}
}
}


 





18.C# program to create a file,check the existence of file and read the contents of the file?
using System;
using System.IO;
namespace FileRead
{
class FileRead
{
public static void Main()
{
string fileName;
while (true)
{
Console.WriteLine("\n-----------MENU-------------\n");
Console.WriteLine("\n 1.Create a File");
Console.WriteLine("\n 2.Existence of the File");
Console.WriteLine("\n 3. Read the content of file");
Console.WriteLine("\n 4. Exit");
Console.WriteLine("\n Enter your choice:");
int ch = int.Parse(Console.ReadLine());
switch (ch)
{
case 1:
Console.Write("\n Enter the filename to create:");
fileName = Console.ReadLine();
Console.WriteLine("\n Write the contents to the File:\n");
string r = Console.ReadLine();
using (StreamWriter fileStr = File.CreateText(fileName))
{
fileStr.WriteLine(r);
}
Console.WriteLine("File is Crreated------");
break;
case 2:
Console.Write("\n Enter the filename:");
fileName = Console.ReadLine();
if (File.Exists(fileName))
{
Console.WriteLine("File exists----");
}
else
{
Console.WriteLine("File does not exist in the current directory!");
}
break;
case 3:
Console.WriteLine("Enter the file name to read the contents:\n");
fileName = Console.ReadLine();
if (File.Exists(fileName))
{
using (StreamReader sr = File.OpenText(fileName))
{
string S = " ";
Console.WriteLine("Here is the content of the file:");
while ((S = sr.ReadLine()) != null)
{
Console.WriteLine(S);
}
Console.WriteLine(" ");
}
}
else
{
Console.WriteLine("File does not exists");
}
break;
case 4:
Console.WriteLine("\n Exiting-----");
return;
default :
Console.WriteLine("\n Invalid choice");
break;
}
}
}
}
}


 
 
 







19.C# program to perform file comparision?

using System;
using System.IO;
namespace Exercise
{
class FileRead12
{
public static void Main()
{
string file1;
string file2;
Console.Write("Enter the First file path:");
file1 = Console.ReadLine();
Console.Write("Enter the Second file path:");
file2 = Console.ReadLine();
if(!File.Exists(file1))
{
Console.WriteLine("First file does not exists!");
}
else if(!File.Exists(file2))
{
Console.WriteLine("Second file does not exists!");
}
else if(File.ReadAllText(file1)==File.ReadAllText(file2))
{
Console.WriteLine("Both files contains the same content");
}
else
{
Console.WriteLine("Contents of files are not same");
}
}
}
}


 
 



















20.C# program to implement IComparable Interface?
using System;
namespace Exercises
{
class Fraction : IComparable
{
int z, n;
public Fraction(int z, int n)
{
this.z = z;
this.n = n;
}
public static Fraction operator +(Fraction a, Fraction b)
{
return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);
}
public static Fraction operator *(Fraction a, Fraction b)
{
return new Fraction(a.z * b.z, a.n * b.n);
}
public int CompareTo(object obj)
{
Fraction f = (Fraction)obj;
if ((float)z / n < (float)f.z / f.n)
return -1;
else if ((float)z / n > (float)f.z / f.n)
return 1;
else
return 0;
}
public override string ToString()
{
return z + "/" + n;
}
}
class ICompInterface
{
public static void Main()
{
Fraction[] a =
{
new Fraction(5,2),
new Fraction(29, 6),
new Fraction(4, 5),
new Fraction(10, 8),
new Fraction(34, 7)
};
Array.Sort(a);
Console.WriteLine("Implementing the IComparable Interface in "+" Displaying Fraction:");
foreach(Fraction f in a)
{
Console.WriteLine(f +" ");
}
Console.WriteLine();
}
}
}

 






21.C# program to create thread pools?

using System;
using System.Threading;
namespace Exercises
{
class ThreadPoolProg
{
public void ThreadFun1(object obj)
{
int loop = 0;
for (loop = 0; loop <= 4; loop++)
{
Console.WriteLine("Thread1 is executing");
}
}
public void ThreadFun2(object obj)
{
int loop = 0;
for (loop = 0; loop <= 4; loop++)
{
Console.WriteLine("Thread2 is executing");
}
}
public static void Main()
{
ThreadPoolProg TP = new ThreadPoolProg();
for (int i = 0; i < 2; i++)
{
ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));
ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));
}
Console.ReadKey();
}
}
}


 


















22.C# program to demonstrate error handling using try,catch and finally block?
using System;
namespace Exercises
{
class ExceptionHandling
{
static void Main(string[] args)
{
Age a = new Age();
try
{
a.displayAge();
}
catch (AgeIsNegativeException e)
{
Console.WriteLine("AgeIsNegativeException: {0}", e.Message);
}
finally
{
Console.WriteLine("Execution of Finally block is done.");
}
}
}
}
public class AgeIsNegativeException : Exception
{
public AgeIsNegativeException(string message) : base(message)
{
}
}
public class Age
{
int age = -5;
public void displayAge()
{
if (age < 0)
{
throw (new AgeIsNegativeException("Age cannot be negative"));
}
else
{
Console.WriteLine("Age is: {0}", age);
}
}
}


 
















23.C# Program to Convert Digits to Words.
Form1.cs [Code]
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
namespace WinFormsApp1
{
public partial class Form1 : Form
{
public Form1()
{
InitializeComponent();
}
private void button1_Click(object sender, EventArgs e)
{
lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));
}
public string NumtoWord(long number)
{
string word = "";
if (number == 0)
{
return "Zero";
}
if (number < 0)
{
return "Minus" + Math.Abs(number);
}
if (number / 10000000 > 0)
{
word += NumtoWord(number / 10000000) + "Corer";
number %= 10000000;
}
if (number / 100000 > 0)
{
word += NumtoWord(number / 100000) + "Lacs";
number %= 100000;
}
if (number / 1000 > 0)
{
word += NumtoWord(number / 1000) + "Thousand";
number %= 1000;
}
if (number / 100 > 0)
{
word += NumtoWord(number / 100) + "Hundred";
number %= 100;
}
if (number > 0)
{
string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",
"Seven", "Eight", "Nine", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",
"Seventeen", "Eighteen", "Nineteen" };
string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",
"Sixty", "Seventy", "Eighty", "Ninety" };
if (number < 20)
{
word += units[number];
}
else
{
word += Tens[number / 10];
if (number % 10 > 0)
{
word += units[number % 10];
}
}
}
return word;
}
}
}
 
 











24.C# Program to Implement PhoneBook.
using System;
using System.Data;
using System.Linq;
using System.IO;
using System.Windows.Forms;
namespace PhoneBook
{
public partial class Form1 : Form
{
public Form1()
{
InitializeComponent();
}
private void btnNew_Click(object sender, EventArgs e)
{
try
{
panel1.Enabled = true;
//Add a New Row:
App.PhoneBook.AddPhoneBookRow(App.PhoneBook.NewPhoneBookRow());
phoneBookBindingSource.MoveLast();
txtName.Focus();
}
catch (Exception ex)
{
MessageBox.Show (ex.Message, "Message", MessageBoxButtons.OK,
MessageBoxIcon.Error);
App.PhoneBook.RejectChanges();
}
}
private void btnEdit_Click(object sender, EventArgs e)
{
panel1.Enabled = true;
txtPhone.Focus();
}

private void btnCancel_Click(object sender, EventArgs e)
{
phoneBookBindingSource.ResetBindings(false);
panel1.Enabled = false;
}
private void btnSave_Click(object sender, EventArgs e)
{
try
{
//End Edit, Save Data To file:
phoneBookBindingSource.EndEdit();
App.PhoneBook.AcceptChanges();
App.PhoneBook.WriteXml(string.Format("{0}//data.dat",
Application.StartupPath));
panel1.Enabled = false;
MessageBox.Show("Number Store Successfully:");
}
catch (Exception ex)
{
MessageBox.Show(ex.Message, "Message", MessageBoxButtons.OK,
MessageBoxIcon.Error);
App.PhoneBook.RejectChanges();
}
}
static PhoneData db;
protected static PhoneData App
{
get
{
if (db == null)
{
db = new PhoneData();
}
return db;
}}
private void Form1_Load(object sender, EventArgs e)
{
string filename = string.Format("{0}//data.dat", Application.StartupPath);
if (File.Exists(filename))
{
App.PhoneBook.ReadXml(filename);
}
phoneBookBindingSource.DataSource = App.PhoneBook;
panel1.Enabled = false;
}

//Code for "DataGridView".
private void dataGridView1_KeyDown(object sender, KeyEventArgs e)
{
if (e.KeyCode == Keys.Delete)
{
if (MessageBox.Show("Are You sure that you want to Delete this Record?",
"Message",
MessageBoxButtons.YesNo, MessageBoxIcon.Question) == DialogResult.Yes)
{
phoneBookBindingSource.RemoveCurrent();
}
}
}
//code for "Search box";
private void txtSearch_KeyPress_1(object sender, KeyPressEventArgs e)
{
if (e.KeyChar == (char)13) //enter Key:
{
if (!string.IsNullOrEmpty(txtSearch.Text))
{
//we can use linq to Query data:
var query = from o in App.PhoneBook
where o.PhoneNo == txtSearch.Text
||
o.FullName.ToLowerInvariant().Contains(txtSearch.Text.ToLowerInvariant())
|| o.Email.ToLowerInvariant() == txtSearch.Text.ToLowerInvariant()
select o;
dataGridView1.DataSource = query.ToList();
}
else
{
dataGridView1.DataSource = phoneBookBindingSource;
}
}
}
}
}
 
 











25.C# Program to Perform Reversal, Padding and Trimming Operations on
string.
using System;
using System.Windows.Forms;
namespace StringOperation
{
public partial class Form1 : Form
{
public Form1()
{
InitializeComponent();
}
private void btnrev_Click(object sender, EventArgs e)
{
string inputString, revstr = "";
int Length;
inputString = txtInput.Text;
Length = inputString.Length-1;
while (Length >= 0)
{
revstr = revstr + inputString[Length];
Length--;
}
MessageBox.Show("Reverse String Is : " + revstr, "Result");
}
private void btntrim_Click(object sender, EventArgs e)
{
string inputString;
inputString = txtInput.Text;
MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");
}
private void btnpad_Click(object sender, EventArgs e)
{
string inputString;
inputString = txtInput.Text;
inputString = inputString.PadLeft(10, '*');
inputString = inputString.PadRight(15, '*');
MessageBox.Show("String After Padding : " + inputString, "Result");
}
}
}
 











26.C# Program to Create a Progress Bar Control.
using System;
using System.ComponentModel;
using System.Threading;
using System.Windows.Forms;
namespace WindowsFormsApplication1
{
public partial class Form1: Form
{
public Form1()
{
InitializeComponent();
}
}
private void Form1_Load(object sender, System.EventArgs e)
{
backgroundWorker1.WorkerReportsProgress = true;
backgroundWorker1.RunWorkerAsync();
}
private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)
{
for (int i = 1; i <= 100; i++)
{
Thread.Sleep(50);
backgroundWorker1.ReportProgress(i);
}
}
private void backgroundWorker1_ProgressChanged(object sender,
ProgressChangedEventArgs e)
{
progressBar1.Value = e.ProgressPercentage;
this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";
}
}
}
 
27.C# Program to perform a number guessing game.



using System;
	using System.Collections.Generic;
	using System.ComponentModel;
	using System.Data;
	using System.Drawing;
	using System.Linq;
	using System.Text;
	using System.Threading.Tasks;
	using System.Windows.Forms;
	
	namespace GUESS_wa_6
	{
	    public partial class Form1 : Form
	    {
	        // Intialising component 
	        static Random r = new Random();
	        int value;
	        int guessnum;
	        int win = 10;
	        int guess = 1;
	        TextBox textBox1;
	        RichTextBox richTextBox1;
	        RichTextBox richTextBox2;
	        Label label4;
	        public Form1()
	        {
	            InitializeComponent();
	            {
	                value = r.Next(10);
	                this.Controls.Clear();
	                this.BackColor = Color.SkyBlue;
	                this.AutoSize = true;
	                this.Padding = new Padding(16);
	
	                Label label = new Label();
	                label.Text = "Pick a number between 1 and 100";
	                label.Bounds = new Rectangle(10, 20, 340, 40);
	                label.Font = new Font("Arial", 16);
	                textBox1 = new TextBox();
	                textBox1.Bounds = new Rectangle(20, 50, 120, 80);
	                textBox1.Font = new Font("Arial", 24);
	                button1 = new Button();
	                button1.Text = " Check Your Guess ";
	                button1.Bounds = new Rectangle(160, 50, 120, 40);
	                button1.BackColor = Color.LightGray;
	                button1.Click += new EventHandler(button1_Click);
	                Label label2 = new Label();
	                label2.Text = "Low Guess";
	                label2.Bounds = new Rectangle(20, 150, 160, 40);
	                label2.Font = new Font("Arial", 18);
	                richTextBox1 = new RichTextBox();
	                richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);
	                richTextBox1.Font = new Font("Arial", 16);
	                Label label3 = new Label();
	                label3.Text = "High Guess";
	                label3.Bounds = new Rectangle(180, 150, 160, 40);
	                label3.Font = new Font("Arial", 18);
	                richTextBox2 = new RichTextBox();
	                richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);
	                richTextBox2.Font = new Font("Arial", 16);
	                label4 = new Label();
	                label4.Bounds = new Rectangle(20, 100, 340, 40);
	                label4.Font = new Font("Arial", 16);
	                this.Controls.Add(label);
	                this.Controls.Add(textBox1);
	                this.Controls.Add(button1);
	                this.Controls.Add(label4);
	                this.Controls.Add(label2);
	                this.Controls.Add(label3);
	                this.Controls.Add(richTextBox1);
	                this.Controls.Add(richTextBox2);
	
	            }
	        }
	
	        private void Form1_Load(object sender, EventArgs e)
	        {
	
	        }
	
	        private void button2_Click(object sender, EventArgs e)
	        {
	
	        }
	
	        private void button1_Click(object sender, EventArgs e)
	        {
	            // Coding of game 
	            if (textBox1.Text == "")
	            {
	                return;
	            }
	            guessnum = Convert.ToInt32(textBox1.Text);
	            textBox1.Text = String.Empty;
	            if (win >= 0)
	            {
	                if (guessnum == value)
	                {
	                    MessageBox.Show("You have guessed the number! \n The number was " + value);
	                    InitializeComponent();
	                }
	                else if (guessnum < value)
	                {
	                    richTextBox1.Text += guessnum + "\n";
	                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));
	
	                }
	                else if (guessnum > value)
	                {
	                    richTextBox2.Text += guessnum + "\n";
	                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));
	
	                }
	                guess++;
	                win--;
	            }
	            if (guess == 11)
	            {
	                label4.Text = "You loose,Correct Guess is " + value;
	            }
	        }
	    }
	}

 
 











28.C#Develop a winform application to create flat clock.
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
namespace clock
{
public partial class Form1 : Form
{
public Form1()
{
InitializeComponent();
timer1.Start();
}
private void Form1_Load(object sender, EventArgs e)
{
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 1000;//1s
timer.Elapsed += Timer_Elapsed;
timer.Start();
}
private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)
{
circularProgressBar1.Invoke((MethodInvoker)delegate
{
circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");
circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM
});
}
}
}
 \









29.Develop an application to create a notepad.
using System;
using System.IO;
using System.Windows.Forms;
using System.Drawing;
namespace Notepad
{
class NotepadForm : Form
{
private string fileName;
private RichTextBox txtContent;
private ToolBar toolBar;
internal NotepadForm()
{
fileName = null;
initializeComponents();

}

void initializeComponents()

{

this.Text = "My notepad";
this.MinimumSize = new Size( 600, 450 );
this.FormClosing += new FormClosingEventHandler( NotepadClosing );
this.MaximizeBox = true;
toolBar = newToolBar();
toolBar.Font = newFont( "Arial", 16 );
toolBar.Padding = newPadding( 4 );
toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);
ToolBarButton toolBarButton1 = newToolBarButton();
ToolBarButton toolBarButton2 = newToolBarButton();
ToolBarButton toolBarButton3 = newToolBarButton();
toolBarButton1.Text = "New";
toolBarButton2.Text = "Open";
toolBarButton3.Text = "Save";
toolBar.Buttons.Add(toolBarButton1);
toolBar.Buttons.Add(toolBarButton2);
toolBar.Buttons.Add(toolBarButton3);
txtContent = newRichTextBox();
txtContent.Size = this.ClientSize;
txtContent.Height -= toolBar.Height;
txtContent.Top = toolBar.Height;
txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right |
AnchorStyles.Top | AnchorStyles.Bottom;
txtContent.Font = newFont( "Arial", 16 );
txtContent.AcceptsTab = true;
txtContent.Padding = newPadding( 8 );

this.Controls.Add(toolBar);
this.Controls.Add( txtContent );
}
private void toolBarClicked (Object sender, ToolBarButtonClickEventArgs e)
{
saveFile();
switch (toolBar.Buttons.IndexOf(e.Button))
{
case 0: this.Text += "My notepad";
txtContent.Text = string.Empty;
fileName = null;
break;
case 1: OpenFileDialog openDlg = newOpenFileDialog();
if (DialogResult.OK == openDlg.ShowDialog())
{

fileName = openDlg.FileName;
txtContent.LoadFile( fileName );
this.Text = "My notepad " + fileName;

}
break;

}
}
void saveFile()
{
if( fileName == null )

{
SaveFileDialog saveDlg = newSaveFileDialog();
if (DialogResult.OK == saveDlg.ShowDialog())
{

fileName = saveDlg.FileName;
this.Text += " " + fileName;

}
}
else
{
txtContent.SaveFile( fileName, RichTextBoxStreamType.RichText );
}
}
private void NotepadClosing(Object sender, FormClosingEventArgs e)
{
saveFile();
}
static void Main (String[] args )
{

Application.Run( new NotepadForm() );
}
}
}
 



30.Develop an application to construct a graphical binary tree where you need to create ,add,search and remove nodes.


using System;
using System.Windows.Forms;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Drawing2D;
namespace BinaryTree
{
partial class BinTreeForm : Form
{
private Node root;
BinTreeForm()
{
InitializeComponent();
this.root = null;
test();
}
void test()
{
textBox1.Text = "5";
btnAdd_Click( btnAdd, null );
textBox1.Text = "3";
btnAdd_Click( btnAdd, null );
textBox1.Text = "2";
btnAdd_Click( btnAdd, null );
textBox1.Text = "1";
btnAdd_Click( btnAdd, null );
textBox1.Text = "4";
btnAdd_Click( btnAdd, null );
textBox1.Text = "7";
btnAdd_Click( btnAdd, null );
textBox1.Text = "6";
btnAdd_Click( btnAdd, null );
textBox1.Text = "8";
btnAdd_Click( btnAdd, null );
}
void btnCreate_Click( object sender, EventArgs e )
{
root = null;
pictureBox1.Image = null;
}
void btnAdd_Click( object sender, EventArgs e )
{
int value = int.Parse( textBox1.Text );
if( root == null )
root = new Node( value );
else
{
if( root.Add( value ) == false )
MessageBox.Show( "The value already exists!" );
}
drawTree();
}
void btnRemove_Click( object sender, EventArgs e )
{
int value = int.Parse( textBox1.Text );
if( root != null )
{
bool status = root.Remove( value, root, ref root );
if( status == false )

{

MessageBox.Show( "the value does not exists" );
}
}
drawTree();
}
void btnSearch_Click( object sender, EventArgs e )
{
string msg;
int value = int.Parse( textBox1.Text );
if ( root == null )
{
msg = "Tree is empty";
} else
{
if( root.Exists( value ) )

{

msg = "Value found";
} else
{

msg = "Value not found";
}
}
MessageBox.Show(msg);
}
void drawTree()
{
if( root != null )
pictureBox1.Image = root.Draw();
else
pictureBox1.Image = null;
this.Update();
}
static void Main()
{
Application.Run( new BinTreeForm() );
}
}
class Node
{
internal Node left { get; set; }
internal Node right { get; set; }
internal int value;
internal int center = 12;
private static Bitmap nodeBg = new Bitmap( 30, 25 );
private static Font font = new Font("Arial", 14);
internal Node( int value )
{
this.value = value;
}
internal bool Add( int value )
{
Node node = new Node( value );
if( value < this.value )
{
if( this.left == null )
{
this.left = node;
return true;
}
else
return this.left.Add( value );
}
else if ( value > this.value )
{
if( this.right == null );
{
this.right = node;
return true;
}
else
return this.right.Add( value );
}
return false;
}
internal bool Remove(int value, Node parent, ref Node root)
{
if ( value < this.value )
{
if( left != null )
{
return left.Remove( value, this, ref root );
}
}
else if (value > this.value)
{
if( right != null )
{
return right.Remove( value, this, ref root );
}
}
else if( value == this.value )
{
bool isLeft = (this == parent.left );
if( left == null && right == null )
{
if( root == this )
root = null;
else
if (isLeft) parent.left = null; else parent.right = null;
} else if (right == null)
{
if (isLeft) parent.left = left; else parent.right = left;
if( root == this )
root = left;
} else
{
if ( right.left == null )
{
right.left = left;
if (isLeft) parent.left = right;
else
parent.right = right;
if( root == this )
root = right;
}
else
{
Node node = right;
while ( node.left.left != null )
node = node.left;
Console.WriteLine( "Node: " + node.value );
this.value = node.left.value;
Console.WriteLine( "here" );
node.left = null;
}
}
return true;
}
return false;
}
public Image Draw()
{
Size lSize = new Size( nodeBg.Width / 2, 0 );
Size rSize = new Size( nodeBg.Width / 2, 0 );
Image lNodeImg = null;
Image rNodeImg = null;
int lCenter = 0, rCenter = 0;
if ( this.left != null )
{
lNodeImg = left.Draw();
lSize = lNodeImg.Size;
this.center = lSize.Width;
lCenter = left.center;
}
if ( this.right != null )
{
rNodeImg = right.Draw();
rSize = rNodeImg.Size;
rCenter = right.center;
}
int maxHeight = ( lSize.Height < rSize.Height ) ? rSize.Height : lSize.Height;
if ( maxHeight > 0 ) maxHeight += 35;
Size resultSize = new Size ( lSize.Width + rSize.Width, nodeBg.Size.Height +
maxHeight );
Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);
Graphics g = Graphics.FromImage(result);
g.SmoothingMode = SmoothingMode.HighQuality;
g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));
g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);
string str = "" + value;
g.DrawString( str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7,
nodeBg.Height / 2f - 12);
Pen pen = new Pen(Brushes.Black, 1.2f);
float x1 = center;
float y1 = nodeBg.Height;
float y2 = nodeBg.Height + 35;
float x2 = lCenter;
var h = Math.Abs(y2 - y1);
var w = Math.Abs(x2 - x1);
if (lNodeImg != null)
{
g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35);
var points1 = new List<PointF>
{
new PointF(x1, y1),
new PointF(x1 - w/6, y1 + h/3.5f),
new PointF(x2 + w/6, y2 - h/3.5f),
new PointF(x2, y2),
};
g.DrawCurve(pen, points1.ToArray(), 0.5f);
}
if (rNodeImg != null)
{
g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35);
x2 = rCenter + lSize.Width;
w = Math.Abs(x2 - x1);
var points = new List<PointF>
{
new PointF(x1, y1),
new PointF(x1 + w/6, y1 + h/3.5f),
new PointF(x2 - w/6, y2 - h/3.5f),
new PointF(x2, y2)
};
g.DrawCurve(pen, points.ToArray(), 0.5f);
}
return result;
}
public bool Exists(int value)
{
bool res = value == this.value;
if (!res && left != null)
res = left.Exists(value);
if (!res && right != null)
res = right.Exists(value);
return res;
}
} 
}
 

 

