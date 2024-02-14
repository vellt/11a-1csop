```c#
static void Main(string[] args)
{
	// PROGRAMOZÁSI TÉTELEK / NEVEZETES ALGORITMUSOK
	// alapvető algoritmusok amiket programozás során használunk
	osszegzesTetele();
	megszamlalasTetele();
	eldontesTetele();
	osszetettFeladat1();
	osszetettFeladat2();
}

/// <summary>
/// GYAKORLÓ
/// "CASIC nevű kínai cég megdönti a vasútipar rekordjait. Készül az 1000 km/h-s vonat."
/// - van-e benne nagybetű
/// - van-e benne kisbetű
/// - van-e benne szám
/// - mennyi betűből áll
/// - mennyi szám van benne
/// - mennyi kisbetű van benne
/// </summary>
private static void osszetettFeladat2()
{
	string szoveg = "CASIC nevű kínai cég megdönti a vasútipar rekordjait. Készül az 1000 km/h-s vonat.";
	task1(szoveg);
}

/// <summary>
/// van-e benne nagybetű
/// </summary>
private static void task1(string szoveg)
{
	// ELDÖNTÉS
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<szoveg.Length)
	{
		if(szoveg[i]>='A' && szoveg[i] <= 'Z')
		{
			vanE = true;
		}
		i++;
	}
}

/// <summary>
/// iskolai verseny. 2 10 főscsoport van. minden tanuló [0,10] közötti
/// pontot szerzett. Írassa ki külön-külön sorba a csoportok eredményeit
/// - mennyi tanuló szerzett az első csoportból 0 pontot [megszámlálás tétele]
/// - volt-e a második csoportban 10 pontot szerző tanuló [eldöntés tétele]
/// - melyik csoport mennyi pontot szerzett összesen [összegzés tétele]
/// </summary>
private static void osszetettFeladat1()
{
	Random r = new Random();
	int[] elsoCsop = feltolt(10, r);
	int[] masodikCsop = feltolt(10, r);
	feladat1(elsoCsop);
	feladat2(masodikCsop);
	feladat3(elsoCsop, masodikCsop);
}

/// <summary>
/// melyik csoport mennyi pontot szerzett összesen [összegzés tétele]
/// </summary>
private static void feladat3(int[] elsoCsop, int[] masodikCsop)
{
	int elsoCsoportOsszpont = 0;
	int masodikCsoportOsszpont = 0;
	for (int i = 0; i < elsoCsop.Length; i++)
	{
		elsoCsoportOsszpont += elsoCsop[i];
		masodikCsoportOsszpont += masodikCsop[i];
	}
	Console.WriteLine($"csop1 összpont: {elsoCsoportOsszpont}");
	Console.WriteLine($"csop2 összpont: {masodikCsoportOsszpont}");

	if (elsoCsoportOsszpont > masodikCsoportOsszpont)
	{
		Console.WriteLine("1. csoport nyert");
	}
	else if(elsoCsoportOsszpont < masodikCsoportOsszpont)
	{
		Console.WriteLine("2. csoport nyert");
	}
	else
	{
		Console.WriteLine("döntetlen");
	}
}

/// <summary>
/// VOLT-E a második csoportban 10 pontot szerző tanuló [eldöntés tétele]
/// </summary>
private static void feladat2(int[] masodikCsop)
{
	bool voltE = false;
	int i = 0;
	while (voltE==false && i<masodikCsop.Length)
	{
		if (masodikCsop[i] == 10)
		{
			voltE = true;
		}
		i++;
	}
	if (voltE == true) Console.WriteLine("volt olyan tanuló aki 10 pontot szerzett.");
	else Console.WriteLine("Nem volt olyan tanuló aki 10 pontot szerzett volna.");
}

/// <summary>
///  mennyi tanuló szerzett az első csoportból 0 pontot [megszámlálás tétele]
/// </summary>
private static void feladat1(int[] elsoCsop)
{
	// megszámlálás tétele
	int szamlalo = 0;
	for (int i = 0; i < elsoCsop.Length; i++)
	{
		if (elsoCsop[i] == 0) szamlalo++;
	}
	Console.WriteLine($"1. feladat: {szamlalo}db");
	
}

// a main metódusban használjuk, hogy feltöltsünk egy tömböt, random számokkal
private static int[] feltolt(int hossz, Random r)
{
	int[] tomb = new int[hossz];
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(11);//[0,10]
	}
	return tomb;
}

private static void eldontesTetele()
{
	// addig fusson míg nem talál olyat ami megfelel a feltételnek
	// azaz van-e 10től nagyobb, ha igen lépjen ki a ciklusból
	// de kezeljük le azt az eshetőséget, hogy nincs benne a feltételnekű
	// megfelelő elem, ekkor végtelen ciklus alakulhat ki, ha nem kezeljük le
	// egy összetett feltétellel a while ciklusban
	int[] tomb = new int[] { 1, 10, 5, 3, 2, 4, 5, 7, 8, 10, 4, 1 };
	bool vanE = false;
	int i = 0;
	// ciklus
	while (vanE==false && i< tomb.Length)
	{
		if (tomb[i] > 10)
		{
			vanE = true;
		}
		i++;
	}
	if (vanE == true) Console.WriteLine("volt 10-nél nagyobb benne");
	else Console.WriteLine("nem volt 10-nél nagyobb benne");
}

private static void megszamlalasTetele()
{
	int[] tomb = new int[] { 3, 5, 2 };
	// MENNYI db páros szám van
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) szamlalo++;
	}
}

private static void osszegzesTetele()
{
	// számoljuk meg az összes elemet
	// kezdő érték beállítása egy 3 elemű tömbnek, így:
	int[] tomb = new int[3];
	tomb[0] = 2;
	tomb[1] = 10;
	tomb[2] = 5;
	// vagy így:
	int[] tomb2 = new int[] { 2, 10, 5 };

	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
		Console.WriteLine(osszeg);
	}

	// konkatenáció/összefűzés
	string szoveg = "";

	string firstname = "John";
	string lastname = "Doe";
	string szokoz = " ";
	// szöveg részeket
	szoveg += firstname;
	szoveg += szokoz;
	szoveg += lastname;
	Console.WriteLine(szoveg); // John Doe

	// karaktereket adunk hozzá
	char[] karakterTomb = new char[] { 'A', 'L', 'M', 'A' };
	string szoveg1 = "";
	for (int i = 0; i < karakterTomb.Length; i++)
	{
		szoveg1 += karakterTomb[i];
	}

}
```