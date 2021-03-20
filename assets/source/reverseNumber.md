## <b>Title</b>: Write a program to get the number and print the revers of the number.


```c#
class Program{
        static void Main(string[] args){
            // Write a program to get the number and print the revers of the number .
            Console.WriteLine("Title: Write a program to get the number and print the revers of the number");

            //input
            Console.Write("Enter Number: ");
            int number = Convert.ToInt32(Console.ReadLine());

            // calling the methods
            int result = reverseNumber(number);
            Console.Write($"Result: {result}");
        }
    
        private static int reverseNumber(int input){
            int revNumber = 0;
            int index = input;
            while(index != 0){
                int removeLastNum = index/10;
                revNumber = (revNumber - removeLastNum) * 10 + index;
                index = removeLastNum;
            }
            return revNumber;
        }
    }
```