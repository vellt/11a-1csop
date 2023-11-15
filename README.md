```c#
// if szerkezet átalakítása switch--ééé

// az alakítható át, ami "if, else if, else" vagy "if, else" láncolatot követ
// ELSE legyen benne
// egy adott értéket hasonlít össze több konstanssal és nem pedig változóval
// logikai operátora szigorúan ==
// if, else if--> case
// else --> default

int vegosszeg = 10_000;
string kedvezmeny = "10%";
string kedv = "10%";
if (kedvezmeny== kedv)
{
	Console.WriteLine($"{vegosszeg*0.9}");
}
else if(kedvezmeny=="50%")
{
	Console.WriteLine($"{vegosszeg*0.5}");
}else
{
	Console.WriteLine("Nincs ilyen kedvezmeny");
}

switch (kedvezmeny)
{
	case "10%":
		Console.WriteLine($"{vegosszeg * 0.9}");
		break;
	case "50%":
		Console.WriteLine($"{vegosszeg * 0.5}");
		break;
	default:
		Console.WriteLine("Nincs ilyen kedvezmeny");
		break;
}

// ez átalakítható??

int ora = 12;
int perc = 30;
if(ora==10 && perc == 30)
{
	Console.WriteLine("Még van 2 órám kezdésig");
}
else if (ora == 12)
{
	Console.WriteLine("Még van fél órám a kezdésig");
}
else {
	Console.WriteLine("Elkéstem");
}

// ez nem alakítható át switch, mert az első if feltételben 2 változót vizsgálok


// ez átalakítható??

int erdemjegy = 5;
if (erdemjegy == 5)
{
	Console.WriteLine("jeles");
}
if (erdemjegy == 4)
{
	Console.WriteLine("Jó");
}
if (erdemjegy == 2)
{
	Console.WriteLine("elégséges");
}

// ez  nem átalakítható teljes funcionalitással, mert ha az első feltétel igaz
// nem hagyja abba a többinek a vizsgálatát

// Random intervallum képzése----------------------------------
Random random = new Random();
int sz = random.Next(10); // [0,9]
// [2,15]
int sz1 = random.Next(14)+2;
// [10,30]
int sz2 = random.Next(21) + 10;
// [-10, 10]
int sz3 = random.Next(21)-10;
// [-20,20]
int sz4 = random.Next(41)-20;
// [-20,-10]
int sz5 = random.Next(11) - 20;
// [-100,-50]
int sz6 = random.Next(51)-100;


// Sorba cserélgetés -->csökkenő
// Rabdom kell generálni 3 [-30,50], 

Random random1 = new Random();
int szam1 = random.Next(81)-30;
int szam2 = random.Next(81)-30;
int szam3 = random.Next(81)-30;
Console.WriteLine($"{szam1} {szam2} {szam3}");
if (szam1 < szam2)
{
	int temp = szam2;
	szam2 = szam1;
	szam1 = temp;
}
if (szam1 < szam3)
{
	int temp = szam3;
	szam3 = szam1;
	szam1 = temp;
}
if (szam2 < szam3)
{
	int temp = szam3;
	szam3 = szam2;
	szam2 = temp;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");
int kulonbseguk = szam1 - szam3;
Console.WriteLine($"{kulonbseguk}");
int absFgg = Math.Abs(kulonbseguk);
if (kulonbseguk < 0)
{
	int abs = kulonbseguk * -1;
	Console.WriteLine($"ennek az abs: {abs}");
}
else
{
	Console.WriteLine($"ennek az abs: {kulonbseguk}");
}


```