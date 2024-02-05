```c#
static void Main(string[] args)
{
	feladat1();
	feladat2();
	feladat3();
	Console.ReadKey();
}

private static void feladat3()
{
	// hozzon létre egy 10 elemű tömb [1,20]-ban töltse fel az elemeit
	// szervezze ki egy külön tömbbe az eredeti tömb 10nél kisebb elemeit
	Random r = new Random();
	int[] tomb = new int[10];
	int hossz = 0; // ezzel megszámoljuk hogy mennyi elemre teljesül az hogy 10 alatti szám
	for (int i = 0; i < tomb.Length; i++)
	{
		// feltöltjük a tömb i. elemét
		tomb[i] = r.Next(20)+1;
		// ezzel megszámoljuk hogy mennyi elemre teljesül az hogy 10 alatti szám
		if (tomb[i] < 10) hossz++;
	}
	// ha van elegalább egy eleme a tömbnek ami 10nél kisebb szám
	// akkor beletöltjük egy új tömbbe ezt/ezeket az értékeket
	if (hossz != 0)
	{
		int index = 0; // arra kell hogy a tizAlatt tömb elemeit fel tudjuk tölteni
		int[] tizAlatt = new int[hossz]; // létre hozzuk az új tömböt
		// körbenézzük az eredeti tömböt, ha találunk egy olyan értéket ami 10 alatti
		// akkor azt bele töltjük az új tömbbe
		for (int i = 0; i < tomb.Length; i++)
		{
			if(tomb[i] < 10)
			{
				tizAlatt[index]= tomb[i]; // bele töltjük az új tömbbe
				// majd egyel növeljük az indexet hogy az új tömb következő elemét tudjuk lehivatkozni
				// a következő lépésben:
				index++; 
			}
		}
		// írassuk ki qa tizAlatt tömb elemeit
		for (int i = 0; i < tizAlatt.Length; i++)
		{
			Console.Write($"{tizAlatt[i]} ");
		}
	}
	// ha nincs 10nél kisebb eleme:
	else Console.WriteLine("nincs 10 alatti eleme");
}

private static void feladat2()
{
	// készítsünk egy string tömböt, 3 eleműt. Nevezzük el szekrénynek
	// Kérjünk be a konzolról ruhaneműket és töltsük fel velük ezt a tömböt
	string[] szekreny = new string[3];
	for (int i = 0; i < szekreny.Length; i++)
	{
		szekreny[i] = Console.ReadLine();
	}
	// majd írassuk ki a szekrény tartamát
	Console.Write("A szekrény tartalma \n");
	for (int i = 0; i < szekreny.Length; i++)
	{
		Console.WriteLine($"-{szekreny[i]}");
	}
}

private static void feladat1()
{
	int z = 6;
	int y = 6;
	// 1 dim tömb/vektor
	// előnye hogy nem kell ezer+1 változót létre hoznom,
	// a tömbbe eltárolhatunk egyszerre több azonos típusú értéket
	// mely értékek a memóriában egymás mellett foglalnak le területet

	// három elemű karakter típusú tömb
	// ha primitív típusokból (int, double, char, bool) készítünk tömböt
	// alapból nullával tölti fel kezőértékként, bizonyítsuk:
	char[] tomb = new char[3];
	for (int i = 0; i < tomb.Length; i++)
	{
		// ha nem lenne ott az int cast akkor 3 semmit írna ki a konzolra
		// ugyanis a nulla ASCII kódnak nincs megjeleníthető karakterértéke
		Console.WriteLine((int)tomb[i]);
	}
	
	// 2 dim tömb/ mátrix-----------------------------------------------------
	int[,] matrix = new int[2, 3]; // sor, oszlop
	// int[2,3]: sor, oszlop
	// vagy úgy is felfoghatjuk hogy az elsőben azt mondjuk meg, hogy mennyi 
	// 1 dimenziós/vektorból épüljön fel
	// a másodikkal azt határozzuk meg, hogy egy-egy 1dim tömbje/vektorja hány elemből álljon
	for (int i = 0; i < matrix.GetLength(0); i++) // végig járjuk a vektorjait (2db)
	{
		for (int j = 0; j < matrix.GetLength(1); j++) // végigjárjuk egy-egy vektorjának elemeit (3db)
		{
			Console.Write($"{matrix[i, j]}\t"); // az i. vektor j. eleme
		}
		Console.WriteLine(); // mátrixos nézethez kell, ha kirajzolt egy vektorjának elemit, törjön sort
	}
	Console.WriteLine();

	// mátrix feltöltése [5,9] random számokkal, plusz kiíratni
	Random random = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = random.Next(5) + 5; //[5,9]
			Console.Write($"{matrix[i, j]} ");
		}
		Console.WriteLine();
	}
}
```