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





