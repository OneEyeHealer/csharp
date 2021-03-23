## <b>Title</b>: Write a program to convert date time from one Time zone to other time zone.


```C#
class Program{
        static void Main(string[] args){
            Console.WriteLine("Title: Write a program to convert date time from one Time zone to other time zone.");

            // input
            Console.Write("Enter Country who's timezone you wanted to converted: ");
            string country = Console.ReadLine();

            // method call
            timeZoneConvertTo(country);
        }

        private static void timeZoneConvertTo(string country){
            DateTime currentTime = DateTime.Now;
            try{
                Console.WriteLine(TimeZoneInfo.ConvertTimeBySystemTimeZoneId(currentTime, TimeZoneInfo.Local.Id, $"{country} Standard Time"));
            }catch(Exception e){ // gerneral approach
                Console.WriteLine(e.Message);
            }
            // or specific approach
            //  catch(TimeZoneNotFoundException){
            //     Console.WriteLine($"'{country}' Standard Time zone Does't exit in Registry.");
            // }catch(InvalidTimeZoneException){
            //     Console.WriteLine($"'{country}' Standard Time zone Data Corrupted in Registry.");
            // }
        }

    }
```