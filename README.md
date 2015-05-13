# Methods-Homework
FirstLargerThanNeighbours

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;


    class FirstLargerThanNeighbours
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());

            int[] numbers = new int[n];

            for (int j = 0; j < numbers.Length; j++)
            {
                numbers[j] = int.Parse(Console.ReadLine());

            }


            GetIndexOfFirstNumberLarger(numbers);
            
        }

        private static void GetIndexOfFirstNumberLarger(int[] numbers)
        {
            for (int i = 0; i < numbers.Length; i++)
            {


                if (IsLargerThanNeighbours(numbers, i))
                {
                    int z = Array.IndexOf(numbers, numbers[i]);
                    Console.WriteLine(z);
                    break;
                }
                else
                {
                    if (i == numbers.Length - 1)
                    {
                        Console.WriteLine(-1);
                    }
                }
            }
        }

        static bool IsLargerThanNeighbours(int[] numbers, int i)
        {
            bool a;
            if (i == 0)
            {
                a = (numbers[i] > numbers[i + 1]);
            }
            else if (i == numbers.Length - 1)
            {
                a = (numbers[i] > numbers[i - 1]);
            }
            else
            {
                a = (numbers[i] > numbers[i - 1] && numbers[i] > numbers[i + 1])
            }

            return a;
        }
   
    }


