```c#
static void Main(string[] args)
{
	matrix();
	vektor();
	Console.ReadKey();
}

private static void vektor()
{
	int n = Convert.ToInt32( Console.ReadLine());
	string[] tomb = new string[n];
	int szamlalo = 0;
	bool vanE = false;
	for (int i = 0; i < n; i++)
	{
		tomb[i] = Console.ReadLine();
		if (tomb[i].Length == n)
		{
			szamlalo++;
		}

	}
	Console.WriteLine(szamlalo);
	for (int j = 0; vanE == false && j < n; j++)
	{
		string szoveg = tomb[j];
		char elsoKarakter = szoveg[0];
		char utolsoKarakter = szoveg[szoveg.Length-1];
		if (elsoKarakter == utolsoKarakter)
		{
			vanE = true;
		}
	}
	Console.WriteLine(vanE ? "Van" : "Nincs");

	for (int i = 0; i < tomb.Length; i++)
	{
		int szamlalo2 = 0;
		string szoveg = tomb[i];
		for (int j = 0; j < szoveg.Length; j++)
		{
			if (szoveg[j] == 'A' || szoveg[j] == 'E')
			{
				szamlalo2++;
			}
		}
		Console.WriteLine($"A(z) {szoveg} {szamlalo2} darab msh volt a szóban");
	}



}

private static void matrix()
{
	int[,] homerseklet = new int[12, 30];
	Random r = new Random();
	double osszAtlag = 0;
	for (int honap = 0; honap < homerseklet.GetLength(0); honap++)
	{
		double osszHomerseklet = 0;
		for (int nap = 0; nap < homerseklet.GetLength(1); nap++)
		{
			homerseklet[honap, nap] = r.Next(26)-15; //[-15,10]
			osszHomerseklet += homerseklet[honap, nap];
		}
		double adotthonapAtlaga = osszHomerseklet / 30; // homerseklet.GetLength(1)
		osszAtlag += adotthonapAtlaga;
	}
	double evesAtlag = osszAtlag / 12;
	Console.WriteLine(evesAtlag);

	bool vanE = false;

	for (int honap = 0; vanE==false && honap < homerseklet.GetLength(0); honap++)
	{
		int osszhomerseklet = 0;
		for (int nap = 0; nap < homerseklet.GetLength(1); nap++)
		{
			osszhomerseklet += homerseklet[honap, nap];
		}
		double atlag = osszhomerseklet / 30.0;
		if (evesAtlag>atlag)
		{
			vanE = true;
		}
	}
	Console.WriteLine(vanE ? "van olyan amelyik az éves átlag  alatt van " : "nincs olyan amelyik az éves átlag alatt van ");
	bool van = false;
	for (int honap = 0; van==false && honap < homerseklet.GetLength(0); honap++)
	{
		for (int nap = 0; van==false && nap < homerseklet.GetLength(1); nap++)
		{
			if(homerseklet[honap,nap]==-2)
			{
				van = true;

			}
		}
	}
	Console.WriteLine(van ? "van" : "nincs");
}
```