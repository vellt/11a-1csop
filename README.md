```c#
static void Main(string[] args)
{
	bevezeto();
	//programozozási tételek:
	//gyakran használatos algoritmusok a programozásban, tömbökre épül

	osszegzesTetele();
	osszegzesTetele1Feladat();
	osszegzesTetele2Feladat();

	megszamolasTetele();
	megszamolasTetele1Feladat();

	Console.ReadKey();
}

private static void megszamolasTetele1Feladat()
{
	// 12 egész szám [-50, 50]-ban feltöltve. Mennyi pozitív mennyi negatív van
	Random r = new Random();
	int[] tomb = new int[12];
	int poz = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50;
		if (tomb[i] >= 0) poz++;
	}
	Console.WriteLine($"pozitív: {poz}");
	Console.WriteLine($"negatív: {tomb.Length-poz}");
}

private static void megszamolasTetele()
{
	// mennyi olyan eleme van a tömbnek amely egy adott feltételnek megfelel
	// összeg=összeg+1
	// összeg+=1
	// összeg++

	// nézzük meg h mennyi 'e' betű van a következő karakter tömbben
	char[] karakterTomb = new char[3];
	karakterTomb[0] = 'e';
	karakterTomb[1] = 'z';
	karakterTomb[2] = 'e';

	int osszeg = 0;
	for (int i = 0; i < karakterTomb.Length; i++)
	{
		if (karakterTomb[i] == 'e') osszeg++;
	}
	Console.WriteLine($"ennnyi 'e' betű van benne: {osszeg}");

	// ugyan ez string-ben
	// (láthatjuk, hogy a string tényleg úgy viselkedik, mint egy tömb, pontosabban egy karakter tömb)
	string szoveg = "eze";
	int stringOsszeg = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == 'e') stringOsszeg++;
	}
	Console.WriteLine($"A stringben {stringOsszeg} darab 'e' betű van.");

	// hozzunk létre egy 5 elemű tömböt 
	// kezdő értékkel töltsükü fel, számoljuk meg,
	// hogy mennyi 0tól nagyobb értéke vanó
	int[] szamok = new int[5];
	int szamlalo = 0;
	Random random = new Random();
	for (int i = 0; i < szamok.Length; i++)
	{
		szamok[i] = random.Next(101)-50; // [-50, 50]
		Console.Write($"{szamok[i],5}"); // ez a vessző 5, azt jelenti, hogy minden karakter 5 szóköznyi helyet foglal
		if (szamok[i]>0) szamlalo++;
	}
	Console.WriteLine();
	Console.WriteLine($"ennyi 0-tol nagyobb számod van: {szamlalo}");
}

private static void osszegzesTetele2Feladat()
{
	// 8 egész számú tömböt hozzunk létre [0,100] RANDOM
	// majd az elemeit egy sorba írassuk ki,
	// és vegye az átlagát a számokkal 3 tizedes pontosan
	Random r = new Random();
	int[] tomb = new int[8];
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101);
		Console.Write($"{tomb[i],5}");
		osszeg += tomb[i];
	}
	for (int i = 0; i < 2; i++) Console.WriteLine(); // 2 sortörés
	Console.WriteLine($"átlag: {Math.Round(osszeg / (double)tomb.Length, 3)}");
}

private static void osszegzesTetele1Feladat()
{
	char[] tomb = new char[4];
	tomb[0] = 'A';
	tomb[1] = 'L';
	tomb[2] = 'M';
	tomb[3] = 'A';
	// karaktertömb elemeinek az ASCII kódbeli összegét számolja ki
	int osszeg = 0;
	// karaktertömbből gyártsunk stringet gyártunk
	string osszefuzes = "";
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i]; // ez számként kezeli a karaktert
		osszefuzes += tomb[i]; // ez folyamatosan összefűzi stringbe a karaktert
	}
	Console.WriteLine(osszeg);
	Console.WriteLine(osszefuzes);
}

private static void osszegzesTetele()
{
	// tömbök elmeinek az összegét adja vissza:
	// összeg=összeg+aktuális elem
	// összeg+=aktuális elem

	int[] tomb = new int[3];
	tomb[0] = 10;
	tomb[1] = 5;
	tomb[2] = 6;

	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg = osszeg + tomb[i];
		// osszeg += tomb[i];
	}
	Console.WriteLine($"összegük: {osszeg}"); //21
}

private static void bevezeto()
{
	// a tömböknek egyik nagy előnye hogy nem kell ezer meg egy 
	// változót létrehozni a különböző értékeknek
	// a tömbben egyszerre rengeteg értéket el tudok menteni
	int sz1 = 6;
	int sz2 = 7;
	// három elemű int tömb, kezőértékei 3 nulla
	int[] tomb = new int[3];
}
```