```c#
static void Main(string[] args)
{
	// összegzés: összeadom a tömb értékeit + konkatenációra is használjuk
	// megszámlálás: FELTÉTEL mentén megszámolom azokat az értékeket amik ennek megfelelnek
	// eldöntés tétele: ELDÖNTI, hogy van-e a tömbben egy adott tulajdonságú elem. Amint talál a ciklus leáll
	osszegzesTeteleGyak();
	megszamlalasTetele();
	eldontesTetele();
	int dec = binToDec("1000101");
	string bin = decToBin(69);
	string bin2 = decToBin2(69);
}

private static string decToBin2(int dec)
{
	string binReverse = "";
	while (dec!=0)
	{
		binReverse += dec % 2;
		dec /= 2;
		// vagy dec=dec/2;
	}
	string bin = "";
	for (int i = binReverse.Length - 1; i >= 0; i--)
	{
		bin += binReverse[i];
	}
	return bin;
}

private static string decToBin(int dec)
{
	int hatvany = 0;
	while (Math.Pow(2,hatvany)<=dec)
	{
		hatvany++; 
	}
	hatvany-- ;

	string bin = "";
	int osszeg = 0;
	for (int i = hatvany; i >= 0; i--)
	{
		if (osszeg + Math.Pow(2, i) <= dec)
		{
			osszeg += (int)Math.Pow(2, i);
			bin += 1;
		}
		else
		{
			bin += 0;
		}
	}

	return bin;

}

private static int binToDec(string bin)
{
	int dec = 0;
	int kitevo = 0;
	for (int i = bin.Length - 1; i >= 0; i--)
	{
		if (bin[i] == '1')
		{
			dec+=(int) Math.Pow(2, kitevo);
		}
		kitevo++;
	}
	return dec;
}

private static void eldontesTetele()
{
	// van-e benne páros
	// addig kell futnia amig nem talál egy olyan számot
	// ami a feltételnek megfelel
	// gondoskodni kell arról hogy egyáltalán nem találunk
	// benne olyan számot/értéket akkor viszont
	// végtelen ciklus ne képződjön
	int[] tomb = new int[] { 1, 5, 3, 7, 3, 9 };
	int index = 0;
	bool vanE = false;
	while (vanE==false && index<tomb.Length)
	{
		if(tomb[index] % 2 == 0)
		{
			vanE = true;
		}
		index++;
	}
	
}

private static void megszamlalasTetele()
{
	// egy feltétel mentén nézzük meg az értékeket, ahol van találat
	// növeljük a számláló értékét eggyel
	int[] tomb = new int[] { 1, 2, 3, 4, 5, 6 };
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2==0)
		{
			szamlalo++;
		}
	}

}

private static void osszegzesTeteleGyak()
{
	// osszeg=osszeg+aktualis_elem
	int[] tomb = new int[5];
	tomb[0] = 6;
	tomb[1] = 6;
	tomb[2] = 6;
	tomb[3] = 6;
	tomb[4] = 6;

	// összegük
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		//osszeg =osszeg+ tomb[i];
		osszeg += tomb[i];
	}


	// konkatenáció/összefűzés
	string szoveg = "";
	szoveg += 'a';
	szoveg += "a";
	szoveg += "alm";
	// dinamikusan feltölteni egy szöveget egy int tömbből
	int[] ascii = new int[] { 65, 64, 66, 70 };
	szoveg = "";
	for (int i = 0; i < ascii.Length; i++)
	{
		szoveg += (char)ascii[i];
	}
	// dinamikusan feltölteni egy szöveget egy karakter tömbből
	szoveg = "";
	char[] chars = new char[] { 'B', 'K', 'V' };
	for (int i = 0; i < chars.Length; i++)
	{
		szoveg += chars[i];
	}
}
```