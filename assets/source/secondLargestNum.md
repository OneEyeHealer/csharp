## <b>Title</b>: Write a program to capture the Student marks and print the second highest student marks. Using object-oriented programming.


```c#
class Program{
        static void Main(string[] args){
            // Write a program to capture the Student marks and print the second highest student marks. Using object-oriented programming.
            Console.WriteLine("Title: Write a program to capture the Student marks and print the second highest student marks. Using object-oriented programming");

            //input
            Console.Write("How many Student taken the test: ");
            int size = Convert.ToInt32(Console.ReadLine());

            // input for start and end
            Console.Write("Enter min and max Value: ");
            int[] studentMarks = marksArrayList(Console.ReadLine().Split(" "), size);

            // calling the methods
            int result = secondLargest(studentMarks, size);
            if(result == 0) Console.WriteLine("No Second Largest Element is Present");
            Console.WriteLine($"Result: {result}");
        }

        private static int[] marksArrayList(string[] marks, int size){
            int[] marksArray = new int[size];
            for(int i=0; i< size; i++) marksArray[i] = int.Parse(marks[i]);

            return marksArray;
        }

        private static int secondLargest(int[] marks, int size){
            int first, second;
            int i = -1;
            if(size < 2) return 0;

            first = second = int.MinValue;
            while(i++ < size-1){
                if(marks[i] > first){
                    second = first;
                    first = marks[i];
                }
                else if(marks[i] > second && marks[i] != first) second = marks[i]; //when first and second have same value or repeated value.
            }
            if(second == int.MinValue) return 0;  // no second largest present
           return second; // second largest present
        }
    }
```