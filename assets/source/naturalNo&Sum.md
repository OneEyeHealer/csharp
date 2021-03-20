## <b>Title</b>: Display first `n` Natural numbers except `user-input` and its Sum - dynamicaly

```c#
class Program{
        static void Main(string[] args){
            // input for start and end
            Console.Write("Enter starting and Ending Value: ");
            var data = Console.ReadLine().Split(' ');
            var startNum = int.Parse(data[0]);
            var endNum = int.Parse(data[1]);

            Console.Write("Enter Size of Expected Value: ");
            int size = Convert.ToInt32(Console.ReadLine());

            Console.Write("Enter Expected Values: ");
            int[] exceptValues = expectedArray(Console.ReadLine().Split(' '), size);

            // print the nautural num except {user input} - dynamic input
            int dynamicArraySum = printNaturalDynamically(startNum - 1, endNum, exceptValues);

            // sum of nautral number except {user input} - custome input
            int result = printNaturalWithException(dynamicArraySum, exceptValues);

            Console.Write($"{result}");
        }

        private static int[] expectedArray(string[] array, int size){
            int[] intArray = new int[size]; 
            for(int i = 0; i < size; i++){
                intArray[i] = int.Parse(array[i]);
            }
            return intArray;
        }

        private static int printNaturalDynamically(int start, int end, int[] exceptValues){
            Console.WriteLine("\nTitle: Display natural numbers except userInput - Dynamically");
            int arraySum = 0;
            while(start++ < end){
                arraySum += start;
                bool a = Array.Exists(exceptValues, element => element == start);
                    if (a) continue;
                    Console.Write($" {start} ");
            }
            return arraySum;
        }

        private static int printNaturalWithException(int arraysum, int[] exceptValuesSum){
            Console.Write("\n\nTitle: Sum of Natural Numbers except userInput: ");
            return arraysum - exceptValuesSum.Sum();
        }
    }
```

