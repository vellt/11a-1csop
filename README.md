```c#
static void Main(string[] args)
{
	string bin = decToBin(40);
	int dec = binToDec(bin);
	Console.WriteLine(bin);
	Console.WriteLine(dec);
	Console.ReadKey();
}

private static int binToDec(string bin)
{
	int dec = 0;
	int hatvany = 0;
	for (int i = bin.Length - 1; i >= 0; i--)
	{
		if (bin[i] == '1')
		{
			dec += (int)Math.Pow(2, hatvany);
		}
		hatvany++;
	}
	return dec;
}

private static string decToBin(int dec)
{
	string bin = "";

	int kezdohatvany = 0;
	while (Math.Pow(2,kezdohatvany)<dec) kezdohatvany++;
	kezdohatvany--;

	int osszeg = 0;
	for (int i = kezdohatvany; i >= 0; i--)
	{
		if (osszeg + (int)Math.Pow(2, i) <= 40)
		{
			osszeg += (int)Math.Pow(2, i);
			bin += "1";
		}
		else bin += "0";
	}
	return bin;
}
```