```c#
static void Main(string[] args)
{
	tobbSoros();
	egysoros();
	
	Console.ReadKey();
}

private static void tobbSoros()
{
	string beolvas = File.ReadAllText("olvass_be.txt");
	beolvas += " ";
	//Console.WriteLine(beolvas);
	string szabaly = "";
	for (int i = 0; i < beolvas.Length; i++)
	{
		if (beolvas[i] != ' ')
		{
			szabaly += beolvas[i];
		}
		else
		{
			// szóközt találtunk, akk megvizsgáljuk hogy eddig mi került
			// a szabaly változóba
			if (szabaly == "nl")
			{
				Console.WriteLine();
			}
			else
			{
				// első karakter az szám
				int ismetlesSzama = Convert.ToInt32(szabaly[0].ToString());
				string karakterParancs = "";
				char kiir = ' ';
				for (int j = 1; j < szabaly.Length; j++) karakterParancs += szabaly[j];
				if (karakterParancs == "sp") kiir = ' ';
				else if (karakterParancs == "bS") kiir = '\\';
				else if (karakterParancs == "sQ") kiir = '\'';
				else kiir = Convert.ToChar(karakterParancs);
				for (int j = 0; j < ismetlesSzama; j++)
				{
					Console.Write(kiir);
				}
			}
			szabaly = "";
		}
	}
	Console.WriteLine("\n");
}

private static void egysoros()
{
	File.ReadAllText("olvass_be.txt").Split(' ').ToList().Select(x => new { ismetlesSzama = x[0] == 'n' ? 1 : Convert.ToInt32(x[0].ToString()), karakter = x[0] == 'n' ? '\n' : (string.Join("", x.Skip(1)) == "sp" ? ' ' : string.Join("", x.Skip(1)) == "bS" ? '\\' : string.Join("", x.Skip(1)) == "sQ" ? '\'' : x[1]) }).ToList().ForEach(x => { for (int i = 0; i < x.ismetlesSzama; i++) Console.Write(x.karakter); });
}
```