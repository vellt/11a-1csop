```c#
// Oktatóprogram! 
// adjon annyi feladatot amennyit a felh ad meg 
// véletlenszerűen rakjon ki operátort (+,-,*,/)
// minden egyes felathoz képezz 2 random számot [1,9]-ban 
// pl: -5+3=? 
// minden egyes megoldás 1-1 pont 
// összesen 10 pont szerezhető 
// osztályozzuk a tanulót a végén 
// 0-2ig elégtelen 
// 3-4ig elégséges 
// 5-6ig közepes 
// 7-8ig jó 
// 9-10ig jeles
Console.WriteLine("Add meg hogy mennyi feladatot szeretnél");
int feladatokSzama = Convert.ToInt32(Console.ReadLine());
Random random = new Random();
double valasz =0;
int pont = 0;
for (int i = 1; i <=feladatokSzama ; i++)
{
	int szam1 = random.Next(9) + 1;
	int szam2 = random.Next(9) + 1;
	int op = random.Next(4);
	switch (op)
	{
		case 0:
			Console.Write($"{szam1} + {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 + szam2) pont++;
			break;
		case 1:
			Console.Write($"{szam1} - {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 - szam2) pont++;
			break;
		case 2:
			Console.Write($"{szam1} * {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 * szam2) pont++;
			break;
		case 3:
			Console.Write($"{szam1} / {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == szam1 / (double)szam2) pont++;
			break;
	}
}
Console.WriteLine($"ennyi pontot szereztél: {pont}");

double szazalek = Convert.ToDouble(pont) / feladatokSzama * 100;
Console.WriteLine($"ennyi százalékod lett:{szazalek}");
// megnézzük hanyas a dolgozata:
if(szazalek >= 80)
{
	Console.WriteLine("Az érdemjegyed:5");
}
else if(szazalek >= 70)
{
	Console.WriteLine("Az érdemjegyed:4");
}
else if(szazalek >= 60)
{
	Console.WriteLine("Az érdemjegyed:3");
}
else if(szazalek >= 40)
{
	Console.WriteLine("Az érdemjegyed:2");
}
else
{
	Console.WriteLine("Az érdemjegyed:1");
}


Console.ReadKey();
```