```c#
/* DOLGOZATBAN:
- összetett logikai kifejezések
- if else struktúrát átalakítani switch, már ha lehetséges, ha nem akkor mondd meg miért nem
- egyparaméteres random számok generálása, és azokkal való műveletek
- 3 vagy több elem növekvő/csökkenő sorrendbe való cserélgetése
- while/do while ciklus
 */

// sorba rendezgetés-------------------------------------------------------
// (növekvő sorrendbe)
int szam1 = 7;
int szam2 = 6;
int szam3 = 5;


Console.WriteLine($"{szam1} {szam2} {szam3}");
if (szam1 > szam2)
{
	int temp = szam2;
	szam2 = szam1;
	szam1 = temp;
}
if (szam1 > szam3)
{
	int temp = szam3;
	szam3 = szam1;
	szam1 = temp;
}
if (szam2 > szam3)
{
	int temp = szam3;
	szam3 = szam2;
	szam2 = temp;
}
Console.WriteLine($"{szam1} {szam2} {szam3}"); // növekvő sorrenben jelenít meg
Console.WriteLine($"a legkisebb négyzetgyöke: {Math.Round(Math.Sqrt(szam1), 3)}");

// while-----------------------------------------
// 10-1 ig csökkenő sorrendbe számok
int valtozo = 10;
while (valtozo > 0)
{
	Console.WriteLine(valtozo);
	valtozo--;
}

// 1-20ig a páratlan számokat
int x = 1;
while (x < 21)
{
	if (x % 2 != 0)
	{
		Console.WriteLine(x);
	}

	x++;
}

// 1-20ig az összes 5el osztható számot
int y = 1;
while (y < 21)
{
	if (y % 5 == 0)
	{
		Console.WriteLine(y);
	}
	y++;
}

// 1-20 az összes párost, és azok négyzetgyökét,
// 2 tizedesre kerekítve
// pl.: 2-->1.41, 4-->2

int z = 1;
while (z < 21)
{
	if (z % 2 == 0)
	{
		Console.WriteLine($"{z}-->{Math.Sqrt(z):0.00}");
	}
	z++;
}

// (5ért: Írja ki az első N prímszámot, N-->felhasználótol kérje be)

// kérjen be a felh-számokat, és adogassa össze mindaddig, 
// míg 0-t nem adunk értékül

int bekertSzam = 0;
int osszeg = 0;
do
{
	Console.WriteLine("Adjom meg számot:");
	bekertSzam = Convert.ToInt32(Console.ReadLine());
	osszeg = bekertSzam + osszeg;
} while (bekertSzam != 0);

Console.ReadKey();

// if-else ---> switch ------------------------------------------------------
//átalakítható vagy nem switch-é???
int a = 7;
int b = 8;
int c = 10;
if (a == 7)
{
	Console.WriteLine("a és b egyenlő");
}
else if (a == 10)
{
	Console.WriteLine("a és c egyenlő");
}else
{
	Console.WriteLine("a nem egyenlő b-vel sem és c-vel sem");
}
// igen átalakítható úgy, hogy a funkcionalitása megegyezik teljes mértékben
// ugyanis az 'a' változót '=='-el összehasonlítjuk egy konstanssal pl 7, vagy 10
// továbbá lácolt alakban van az if, azaz if--> else if-->else
switch (a)
{
	case 7: Console.WriteLine("a és b egyenlő"); break;
	case 10: Console.WriteLine("a és c egyenlő"); break;
	default: Console.WriteLine("a nem egyenlő b-vel sem és c-vel sem"); break;
}

// kövi
int vegosszeg = 10_000;
string kedvezmeny = "10%";
if (kedvezmeny == "10%")
{
	Console.WriteLine($"a kedvezményes végösszeg: {vegosszeg*0.9}");
}else if (kedvezmeny == "30%")
{
	Console.WriteLine($"a kedvezményes végösszeg: {vegosszeg * 0.7}");
}
else
{
	Console.WriteLine("Nállunk nincsen ilyen kedvezmény!");
}

// igen átalakítható úgy, hogy a funkcionalitása megegyezik teljes mértékben
// ugyanis a 'kedvezmeny' változót '=='-el összehasonlítjuk különböző szöveges konstanssal pl "10%", vagy "30%"
// továbbá lácolt alakban van az if, azaz if--> else if-->else, ami megfeleltethető
// case, case, default formában switch esetében:

switch (kedvezmeny)
{
	case "10%":
		Console.WriteLine($"a kedvezményes végösszeg: {vegosszeg * 0.9}");
		break;
	case "30%":
		Console.WriteLine($"a kedvezményes végösszeg: {vegosszeg * 0.7}");
		break;
	default: Console.WriteLine("Nállunk nincsen ilyen kedvezmény!");
		break;
}

// kövi órán nézünk példát arra, hogy melyik if szerkezet nem alakítható át switch-re és miért
```