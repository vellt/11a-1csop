```c#
static void Main(string[] args)
{
	ketodim();
	egyDim();
	Console.ReadKey();
}

private static void egyDim()
{
	Console.WriteLine("Add meg a szöveges tömb hosszát");
	int hossz = Convert.ToInt32(Console.ReadLine());
	string[] szovegek = new string[hossz];
	for (int i = 0; i < szovegek.Length; i++)
	{
		szovegek[i] = Console.ReadLine();
	}

	// nagybetűsek legyenek kisbetűsek
	for (int i = 0; i < szovegek.Length; i++)
	{
		string szoveg = szovegek[i];
		for (int j = 0; j < szoveg.Length; j++)
		{
			if (szoveg[j] >= 'A' && szoveg[j] <= 'Z')
			{
				Console.Write((char)(szoveg[j] + 32));
			}
			else
			{
				Console.Write(szoveg[j]);
			}
			
		}
		Console.WriteLine();
	}

	// mennyi olyan szó van amiben van a betű
	int szamlalo = 0;
	for (int i = 0; i < szovegek.Length; i++)
	{
		string szoveg = szovegek[i];
		bool van = false;
		for (int j = 0; van==false&& j < szoveg.Length; j++)
		{
			if (szoveg[j] == 'a') van = true;
		}
		if (van) szamlalo++;
	}
	Console.WriteLine(szamlalo);


}

private static void ketodim()
{
	Random r = new Random();
	int[,] honapok = new int[12, 30];

	double osszatlagHomerseklet = 0;
	for (int i = 0; i < honapok.GetLength(0); i++)
	{
		int osszesHomerseklet = 0;
		for (int j = 0; j < honapok.GetLength(1); j++)
		{
			honapok[i, j] = r.Next(21) - 10; //[-10,10]
			osszesHomerseklet += honapok[i, j];
		}
		double atlag = (double)osszesHomerseklet / honapok.GetLength(1);
		osszatlagHomerseklet += atlag; // összegzés t
		Console.WriteLine($"{i+1}. honap atlaghom: {atlag:0.00}");
	}
	double evesAtlag = osszatlagHomerseklet / honapok.GetLength(0);
	Console.WriteLine($"Az éves átlaghőm: {evesAtlag:0.00}");

	bool van = false;
	for (int i = 0; van==false && i < honapok.GetLength(0); i++)
	{
		int osszesHomerseklet = 0;
		for (int j = 0; j < honapok.GetLength(1); j++)
		{
			osszesHomerseklet += honapok[i, j];
		}
		double atlag = (double)osszesHomerseklet / honapok.GetLength(1);
		if (atlag < -3) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");
}
```