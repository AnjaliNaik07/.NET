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

