```c#
//switch---------------------
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

// a felső if-else átalakítása switch-be
switch (honap)
{
	case 1: Console.WriteLine("Január"); break;
	case 2: Console.WriteLine("Február"); break;
	case 3: Console.WriteLine("Március"); break;
	case 4: Console.WriteLine("Április"); break;
	case 5: Console.WriteLine("Május"); break;
	case 6: Console.WriteLine("Június"); break;
	case 7: Console.WriteLine("Július"); break;
	case 8: Console.WriteLine("Augusztus"); break;
	case 9: Console.WriteLine("Szeptember"); break;
	case 10: Console.WriteLine("Oktober"); break;
	case 11: Console.WriteLine("November"); break;
	default: Console.WriteLine("December"); break; // if else-nél a az utolsó else-nek felel meg!
}


//RANDOM--------------------------
Random random = new Random();
int valt= random.Next(10);//0-9
int valt2= random.Next(10,20); //10-19

//[10,50]
int gyak1 = random.Next(41)+10;
//[11,51]
int gyak2 = random.Next(41)+11;
//[-20, -2]
int gyak3 = random.Next(19)-20;
// [-60, -35]
int gyak4 = random.Next(26)-60;
// [-50,25]
int gyak5 = random.Next(76)-50;


/*
 Készítsen egy számkitalálós programot! A gép véletlenszerűen 
találjon ki egy számot 1 és 6 között! A felh-tól kérjen be egy tippet,
és mondja meg, ha sikerült eltalálnia, ha nem mondja meg mire gondolt
a költő!
 */

// ha a while értéke true-->akkor a végtelenségik ismétlődik, 
// false akkor egyáltalán nem fut le a benne megfogalmazott kódrész
while (false)
{
	
	Random random2 = new Random();
	int gep = random2.Next(6) + 1;
	Console.WriteLine("add meg a tipped(1-6 kozott)");
	int tipp = Convert.ToInt32(Console.ReadLine());
	if (gep == tipp) Console.WriteLine("Eltaláltad a gép tippjét");
	else
	{
		Console.WriteLine("Nem találtad el a gép tippjét");
		Console.WriteLine($"A gép amire gondolt: {gep}");
	}
	//Console.WriteLine("A program véget ért! Nyomj entert hogy törlődjön a képernyő tartalma");
	//if(Console.ReadKey().Key==ConsoleKey.Enter) Console.Clear();
}

// 5 random [int] számot [50,100] egy paraméteres randommal
// készítsünk és számoljuk ki
// az összegüket, átlagukat, szorzatukat

Random random3 = new Random();

int szam1 = random.Next(51) + 50;
int szam2 = random.Next(51) + 50;
int szam3 = random.Next(51) + 50;
int szam4 = random.Next(51) + 50;
int szam5 = random.Next(51) + 50;

int osszead = szam1 + szam2 + szam3 + szam4 + szam5;
Console.WriteLine($"összeg:{osszead} ");
Console.WriteLine($"átlag:{osszead/5.0} ");

int szorz = szam1 * szam2 * szam3 * szam4 * szam5;

Console.WriteLine($"szorzat:{szorz}");


/*
 készítsünk egy kő, papír, olló játékot!
A gép (1-3) (egy paraméteres random) generál számot,
1-->kő
2-->papír
3-->olló
Kérjen be a felh-tól egy számot és 
logikailag rakja össze "if-else"-el a működést
irassa ki hogy ki mit választott
 */

// egy lehetséges megoldás:
Random random10 = new Random();
int gepSzam = random10.Next(3) + 1;
Console.WriteLine("Adj egy számot (1-3)[kő, papír, olló]");
int felhSzam = Convert.ToInt32(Console.ReadLine());
// kiíratom a gép mire gondolt
Console.Write("Gép: ");
switch (gepSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}
// kiíratom, hogy a felh. mire gondolt
Console.Write("Felh: ");
switch (felhSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}

if (gepSzam == felhSzam) Console.WriteLine("Döntetlen");
else if (gepSzam == 1 && felhSzam == 3
	|| gepSzam == 2 && felhSzam == 1
	|| gepSzam == 3 && felhSzam == 2
	) Console.WriteLine("gép győzött");
else Console.WriteLine("én nyertem");



//Hármas operátor------------------------------------------------------

// if else átalakítása hármas operátorú kifejezéssé
if (3 > 2) Console.WriteLine("nagyobb");
else Console.WriteLine("kissebb");

// hármas operátor )
Console.WriteLine((3 > 2)? "nagyobb": "kissebb");


// típusok----------------------------------------------
Console.WriteLine('6'.GetType());
Console.WriteLine("6".GetType());
Console.WriteLine(6.GetType());
Console.WriteLine(6.0.GetType());
Console.WriteLine(true.GetType());
```