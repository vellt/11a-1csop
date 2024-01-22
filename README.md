```c#
static void Main(string[] args)
{
	// karakterek/ASCI
	//---------------------------------------------------------
	// hogyan nyerem ki egy karakter ASCII kódját?
	char karakter = 'b';
	Console.WriteLine(karakter); // b
	Console.WriteLine((int)karakter); // 98 <-- így
	// hogyan kényszeríthetem ki, hogy egy szám karakterként jelenjen meg?
	int szam = 67;
	Console.WriteLine(szam); // 67
	Console.WriteLine((char)szam); // A <-- így

	// string, mint tömb
	//---------------------------------------------------------

	// egy szöveg tulajdonságai
	string alma = "alma";
	// első karakter lehivatkozása
	Console.WriteLine(alma[0]);
	// utolsó karakter lehivatkozása
	Console.WriteLine(alma[alma.Length-1]); 

	// döntsük el, hogy van-e az alma változóban 'l' betű
	int szamlalo = 0;
	for (int i = 0; i < alma.Length; i++)
	{
		if (alma[i] == 'l')
		{
			szamlalo++;
		}
	}
	if (szamlalo > 0)
	{
		Console.WriteLine($"van benne! {szamlalo}db");
	}
	else
	{
		Console.WriteLine("nincs benne");
	}

	// a varazsige változót szövegét (értékét) írassa ki fordítva.
	string varazsige = "abrakadabra";
	for (int i = varazsige.Length-1; i>=0; i--)
	{
		Console.Write(varazsige[i]);
	}
	Console.WriteLine();

	// képezzünk monogrammot
	string nev = "kis pista"; 
	Console.Write($"{(char)(nev[0]-32)}.");
	for (int i = 0; i < nev.Length; i++)
	{
	   
		if (nev[i]==' ')
		{
			Console.Write($"{(char)(nev[i+1]-32)}.");
		}
	}
	Console.WriteLine();

	// minden második karakter nagybetűs
	string sz1 = "szalmazsák";
	for (int i = 0; i < sz1.Length; i++)
	{
		if (i%2==0)
		{
			Console.Write(sz1[i]);
		}
		else
		{
			Console.Write((char)(sz1[i]-32));
		}
	}
	Console.WriteLine();

	// minden karakterét számként jelenítsd meg
	// egymás után szóközzel elválasztva
	string sz2 = "almazsák";
	for (int i = 0; i < sz2.Length; i++)
	{
		Console.Write($"{(int)sz2[i]} ");
	}
	Console.WriteLine();


	// -(kötőjel) --> : (kettőspont)
	string mac = "6C-6A-77-C8-E4";
	for (int i = 0; i < mac.Length; i++)
	{
		if (mac[i] == '-')
		{
			Console.Write(":");
		}
		else Console.Write(mac[i]);
	}
	Console.WriteLine();


	// minden szóköz mentén törjünk sort:
	// pl John Doe-->
	// John
	// Doe
	string sz3 = "John Doe";
	for (int i = 0; i < sz3.Length; i++)
	{
		if(sz3[i]==' ')
		{
			Console.WriteLine();
		}
		else Console.Write(sz3[i]);
	}
	Console.WriteLine();

	// ugyan ez csak fordítva írassuk közben ki
	// pl : John Doe-->
	// eoD
	// nohJ
	string sz4 = "John Doe";
	for (int i = sz4.Length-1; i >= 0; i--)
	{
		if (sz4[i] == ' ')
		{
			Console.WriteLine();
		}
		else Console.Write(sz4[i]);

	}
	Console.WriteLine();


	// legyen adott egy mondat és íratsd ki a
	// második szót!
	string sz5 = "szeretem az erdőt";
	int szokozszam = 0;
	for (int i = 0; i < sz5.Length; i++)
	{
		if (sz5[i] == ' ')
		{
			szokozszam++;
		}

		if (szokozszam==1 && sz5[i]!=' ')
		{
			Console.Write(sz5[i]);
		}
	}
	Console.WriteLine();

	// TIKOSÍTÁS VISSZAFEJTÉS
	//---------------------------------------------------------
	string eredetiUzenet = "BANÁN";
	// meghívtuk a Titkosítás függvényt, ami kettő paramétert vár
	string titkositottUzenet= Titkositas(eredetiUzenet, 25);
	// meghívtuk a Visszafejtes függvényt, ami kettő paramétert vár
	string visszafejtettUzenet = Visszafejtes(titkositottUzenet, 25);
	Console.WriteLine(eredetiUzenet); // BANÁN
	Console.WriteLine(titkositottUzenet); // kricc kracc szöveg
	Console.WriteLine(visszafejtettUzenet); // BANÁN

	Console.ReadKey();
}

// függvény, feladatköre hogy eltolja a paraméterül kapott szöveg minden 
// karakterét az eltolas valtozó értékével, amit szintén paraméterként kaptunk meg
// a függvény visszatérési értéke string, azaz szöveg, a függvényblokkba ilyenkor 
// kötelező egy return kulcsszó, ezután csak olyan érték lehet ami azonos stringgel
// hiszen a private static után string áll!
private static string Visszafejtes(string titkositottUzenet, int eltolas)
{
	string visszafejtett = "";
	for (int i = 0; i < titkositottUzenet.Length; i++)
	{
		visszafejtett += (char)(titkositottUzenet[i] - eltolas);
	}
	return visszafejtett;
}

// visszafejésért felel
private static string Titkositas(string uzenet, int eltolas)
{
	string titkositottUzenet = "";
	for (int i = 0; i < uzenet.Length; i++)
	{
		titkositottUzenet += (char)(uzenet[i] + eltolas);
	}
	return titkositottUzenet;
}
```