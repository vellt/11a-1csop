```c#
// while ciklusos feladat
Random random = new Random();
int x = random.Next(100)+1;
int y = 0;
int szamlalo = 0;
while (x != y)
{
	Console.WriteLine("Adjom meg egy tippet");
	y = Convert.ToInt32(Console.ReadLine());
	if(y>x) Console.WriteLine("A számod nagyobb mint amire gondoltam");
	else if(y<x) Console.WriteLine("A számod kisebb amire gondoltam");
	szamlalo += 1;
}
Console.WriteLine("A számot eltaláltad");
Console.WriteLine($"{szamlalo}");


// előírt lépésszámú ciklus --> for
for (int i = 1; i <= 10; i++)
{
	Console.WriteLine($"*, lépés szám: {i}");
} 

//véletlenszerűen 5 egész számot [0,50]
// írjuk ki egymás mellé szóközzel elválasztva

Random random2 = new Random();

for (int i = 1; i <= 5; i++)
{
	int sz = random2.Next(51);
	Console.Write($"{sz} ");
}


// 40 random [-100, 100] számot generáljunk
// for ciklussal, egymás mellé írassuk ki
// egy sorban 8 érték lehet (x%8==0)

Random random3 = new Random();

for (int i = 1; i <= 40; i++)
{
	int sz2 = random3.Next(-100,101);
	Console.Write($"{sz2} ");
	if (i % 8 == 0) Console.WriteLine();
}

// Oktatóprogram!
// 10 feladatot adj a felhasználónak
// minden páros összeadásos feladat
// minden páratlan kivonásos feladat
// minden egyes felathoz képezz 2 random számot
// [-5,15]-ban
// pl: -5+3=?
// minden egyes megoldás 1-1 pont
// összesen 10 pont szerezhető
// osztályozzuk a tanulót a végén
// 0-2ig elégtelen
// 3-4ig elégséges
// 5-6ig közepes
// 7-8ig jó
// 9-10ig jeles
```