## <b>Title</b>: Write a program to generate (min, max) range random numbers.

```c#
class Program{
        static void Main(string[] args){
            // Write a program to generate 20 random numbers.
            Console.WriteLine("Title: Write a program to generate (min, max) range random numbers.");
            try{
                //input
                Console.Write("How many number You want to genreate: ");
                int size = Convert.ToInt32(Console.ReadLine());

                // input for start and end
                Console.Write("Enter min and max Value to Generate Random no: ");
                var data = Console.ReadLine().Split(' ');
                var minNum = int.Parse(data[0]);
                var maxNum = int.Parse(data[1]);

                // calling the methods
                Console.WriteLine($"{size} random integer values:");
                generateRandomNum(size, minNum, maxNum);

            } catch (Exception e) {Console.WriteLine(e.Message);}

        }

        private static void generateRandomNum(int size, int minLimit, int maxLimit){
            try{
                var rand = new Random();
                for (int num = 0; num < size; num++)
                    Console.Write("{0,5:N0}", rand.Next(minLimit, maxLimit));

            } catch(Exception e){Console.WriteLine(e.Message);}
        }
    }
```