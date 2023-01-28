
using System.Collections.Generic;
using System.Linq;
using System.Runtime.InteropServices;
using System.Text;
using System.Threading.Tasks;
namespace ConsoleApp5
{
    class Program
    {
        class GFG
        {
            static float f(float x)
            {
                //  equation
                           
                float f = (float)Math.Pow(x, 3) + 3 * (float)Math.Pow(x, 2) - 1;
                return f;
            }
            static void secant(float p0, float p1, float E)
            {
                float i = 2, xm, p2;
                do
                {


                    // calculate 
   
                    p2 = (p1 - (f(p1) * (p1 - p0)) / (f(p1) - f(p0)));
                    Console.WriteLine(" p{0} = {1}",i,p2);

                    
                    // update the value        
           
                    p0 = p1;
                    p1= p2;
                    // update number of iteration

                    i++;
                    xm = (p1 -( f(p1) * (p1 - p0)) / (f(p1) - f(p0)));

                    // repeat the loop until
                } while (Math.Abs(xm - p2) >= E);
                Console.WriteLine(" p{0} = {1}", i, xm);

                Console.WriteLine("\n Root of the" + " given equation = " + p2);
                Console.WriteLine("No. of " + "iterations = " + i);



            }           




            public static void Main(String[] args)
            {
                // initializing the values
                //p0 = -3; p1 = -2;  E = 0.0001f;
                Console.Write("please enter X0=");
                float p0 = float.Parse(Console.ReadLine());
                Console.Write("\nplease enter X1=");
                float p1 = float.Parse(Console.ReadLine());
                Console.Write("\nwhen we stop=");
                float E = float.Parse(Console.ReadLine());
                Console.WriteLine("\n__________________________\n");
                secant(p0, p1, E); 
Console.ReadKey();
            }
        }
    }
}

