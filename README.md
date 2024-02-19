```c#
static void Main(string[] args)
{
	// összegzés:
	// - számok/ karakaterek összeadása
	// megszámlálás:
	// - feltétel mentén megszámoljuk a tömb elemeit
	// eldöntés:
	// - true/false értékkel tér vissza, és addig megy míg nincs találat
	// de egyben a végtelen ciklust ki kell kerülnünk
	osszegzes();
	megszamlalas();
	elontesTetele();
	matrix();
	decToBin();
	binToDec();
	Console.ReadKey();
}

private static void binToDec()
{
	int dec = 0;
	string bin = "11011";
	int hatvany = 0;
	for (int i = bin.Length - 1; i >= 0; i--, hatvany++)
	{
		if (bin[i] == '1')
		{
			dec += (int)Math.Pow(2, hatvany);
		}
	}
	Console.WriteLine(dec);
}

private static void decToBin()
{
	string bin = "";
	int dec = 6;
	while (dec!=0)
	{
		if (dec % 2 == 0) bin += 0;
		else bin += 1;
		dec /= 2;
	}
	for (int i = bin.Length - 1; i >= 0; i--)
	{
		Console.Write(bin[i]);
	}
	Console.WriteLine();
}

private static void matrix()
{
	// 2 dimenziós tömb
	int[,] matrix = new int[2, 3]
	{
		{3,2,4},
		{5,8,2},
	};
	Console.WriteLine(matrix[1,0]); // 5
	Console.WriteLine(matrix[0,2]); // 4
	Console.WriteLine(matrix[1,1]); // 8

	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++) // sorokat pörgeti
	{
		for (int j = 0; j < matrix.GetLength(1); j++) // egy-egy sor elemeit
		{
			matrix[i, j] = r.Next(10); //[0,9]
		}
	}
	// kiíratás
	for (int i = 0; i < matrix.GetLength(0); i++) // sorokat pörgeti
	{
		for (int j = 0; j < matrix.GetLength(1); j++) // egy-egy sor elemeit
		{
			Console.Write($"{matrix[i, j]} ");
		}
		Console.WriteLine();
		// Console.Write("\n");
	}
}

private static void elontesTetele()
{
	int[] tomb = new int[3] { 2, 4, 6 };
	bool vanE = false;
	for (int i = 0; vanE=false && i<tomb.Length; i++)
	{
		if (tomb[i] % 4 == 0) vanE = true;
	}
	Console.WriteLine(vanE ? "van" : "nincs");
}

private static void megszamlalas()
{
	int[] tomb = new int[3] { 2, 4, 6 };
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 4 == 0) szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

private static void osszegzes()
{
	int[] tomb = new int[3] { 2, 4, 6 };
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	Console.WriteLine(osszeg);
}
```