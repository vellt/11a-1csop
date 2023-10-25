```c#
/*
 két érték megcserélése
 */
string fanta ="FANTA"; 
string kola = "kóla";
string ideiglenes = "";
ideiglenes = kola; // kóla
kola = fanta; // fanta
fanta = ideiglenes; // kóla


/*
 kérj be 2 értéket és cseréld meg (alkalmazz segéd változót)
 */
Console.WriteLine("Add meg az a értékét");
int a = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Add meg a b értékét");
int b = Convert.ToInt32(Console.ReadLine());
Console.WriteLine($"az 'a' értéke: {a} a 'b' értéke: {b}");
int temp = a;
a = b;
b = temp;
Console.WriteLine($"az 'a' értéke: {a} a 'b' értéke: {b}");




/* nem használsz változót, 3 lépésből megoldható (interjú kérdés)
 int a=10;
 int b=5;
	b-->10
	a-->5
 
 */
int x = 6;
int y = 3;
x = y + x; //9
y = x - y; //6
x = x - y; //3

// rendezzünk sorba 3 db véletlen [20,40] számot növekvőbe
Random r = new Random();
int sz1 = r.Next(21)+20;
int sz2 = r.Next(21)+20;
int sz3 = r.Next(21)+20;
Console.WriteLine($"{sz1} {sz2} {sz3}");
if (sz1 > sz2)
{
	int temp1 = sz1;
	sz1 = sz2;
	sz2 = temp1;
}
if (sz1>sz3)
{
	int temp1 = sz1;
	sz1 = sz3;
	sz3 = temp1;
}
if (sz2 > sz3)
{
	int temp1 = sz2;
	sz2 = sz3;
	sz3 = temp1;
}
Console.WriteLine($"{sz1} {sz2} {sz3}");
Console.ReadKey();
```