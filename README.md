```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace gyak_11a_1csop_2023_10_11
{
    class Program
    {
        static void Main(string[] args)
        {
            // logikai operátorok
            // ==, !=, <, >, <=, >=
            // logikai kapuk:
            // AND (és): && (altgr +c)
            // OR (vagy): || (altgr + w)
            // NOT (negáció): ! (shift + 4)

            // true, false --> bool
            bool logikaiKif = !(1 == 0) || (1>2); 
            Console.WriteLine(logikaiKif); // false

            /*
             Írjunk egy kifejezést, amely azt ellenőrzi, hogy egy szám 
            páros ÉS pozitív is
             */

            Console.WriteLine("adj meg egy értéket");
            int ertek = Convert.ToInt32(Console.ReadLine());
            if ((ertek % 2 == 0) && (ertek >= 0))
            {
                Console.WriteLine("ez a szám páros és pozitív");
            }
            else if (!(ertek % 2 == 0) && (ertek >= 0))
            {
                Console.WriteLine("ez a szám : PÁRATLAN ÉS POZITÍV ");
            }
            else if ((ertek % 2 == 0) && !(ertek >= 0))
            {
                Console.WriteLine("Ez a szám páros és negatív");
            }
            else if (!(ertek % 2 == 0) && !(ertek >= 0)) 
            {
                Console.WriteLine("Páratlan és Negatív");
            }



            /*
             * összetett logikai kifejezéssel helyettesítsük az 
             * alábbi egyszerű kifejezést
             */

            Console.WriteLine("Add meg az x értékét");
            int x = Convert.ToInt32(Console.ReadLine());

            if ((x > Math.Pow(2, 3) % 2) && x < (Math.Sqrt(16) % 4 + 1)) // 1
            {
                Console.WriteLine("ÍRÁS");
            }
            else if ((x > (Math.Sqrt(16) - 5)) && x < (Math.Abs((Math.Pow(2, 2) + 3) * -1) % 2)) // 0
            {
                Console.WriteLine("FEJ");
            }



            // írjunk egy kif-t ami azt vizsgálja h egy szám osztható 3-al,
            // vagy 5-el, de nem mind2-vel

            Console.WriteLine("add meg az y értékét");
            int y = Convert.ToInt32(Console.ReadLine());

            if (((y % 3 == 0) || (y % 5 == 0)) && !((y % 3 == 0) && (y % 5 == 0)))  
            {
                Console.WriteLine("Ez egy olyan szám ami 3-al és 5-el oszztható de nem mind a kettővel.");
            }

            /*
             4el oszható és 100al nem osztható!
             */
            Console.WriteLine("Add meg az évet, és megmondom h szökőév-e");

           
            int c = Convert.ToInt32(Console.ReadLine());

            if ((c % 4 == 0) && !(c % 100 == 0))
            {
                Console.WriteLine("az egy olyan év ami szököév");
            }

            /*
             Vizsgáljuk meg a bekért telefonszámot, hogy milyen szolgáltatóhoz
            tartozik
             */

            Console.WriteLine("Add meg a 06 utáni telefonszámod");
            string teloszam = Console.ReadLine();
            if (teloszam.Length==9)
            {
                // valid
                if (teloszam[0] == '7') Console.WriteLine("Voda");
                else if (teloszam[0] == '2') Console.WriteLine("Yettel");
                else if (teloszam[0] == '3') Console.WriteLine("telekom");
                else if (teloszam[0] == '5') Console.WriteLine("Digi");
            }
            else Console.WriteLine("Nem valós a telószám");
             
            switch (teloszam.Length)
            {
                case 9:
                    switch (teloszam[0])
                    {
                        case '7': Console.WriteLine("voda"); break;
                        case '2': Console.WriteLine("Yettel"); break;
                        case '3': Console.WriteLine("telekom"); break;
                        case '5': Console.WriteLine("digi"); break;
                    }
                    break;
                default: Console.WriteLine("nem valós telefonszám"); break;
            }

            /*
             Írjunk egy programot, amely bekéri a hónap
            számát (1-12), majd kiírja a hónap nevét
            a megadott szám alapján, 
             */

            Console.WriteLine("kérlek add meg a hónap számát");
            int honap = Convert.ToInt32(Console.ReadLine());

            if (honap == 1) Console.WriteLine("Január");
            else if (honap == 2) Console.WriteLine("Február");
            else if (honap == 3) Console.WriteLine("Március");
            else if (honap == 4) Console.WriteLine("Április");
            else if (honap == 5) Console.WriteLine("Május");
            else if (honap == 6) Console.WriteLine("Június");
            else if (honap == 7) Console.WriteLine("Július");
            else if (honap == 8) Console.WriteLine("Augusztus");
            else if (honap == 9) Console.WriteLine("Szeptember");
            else if (honap == 10) Console.WriteLine("Oktober");
            else if (honap == 11) Console.WriteLine("November");
            else Console.WriteLine("December");

        }
    }
}
```