```c#
/* képezzünk intervallumokat */
Random random = new Random();

//[60,80]
int sz1 = random.Next(21)+60;
//[0,7]
int sz2 = random.Next(8);
//[-50,60]
int sz3 = random.Next(111) - 50;
//[-60,-20]
int sz4 = random.Next(41) - 60;

//-------------------------------------

bool igazE = false;
// if else
if (2 == 3) igazE = false;
else igazE = true;
// hármas operátor
igazE = (2 == 3) ? false : true;

//-------------------------------------
/*
 2 véletlenszámot generáljunk [0,10] és írjuk ki a számokat
a képernyőre, majd azt h melyik szám a nagyobb! (hármas operátorral)
 */

Random random1 = new Random();

int szam1 = random1.Next(11);
int szam2 = random1.Next(11);

if (sz1 > sz2) Console.WriteLine($"a {sz1} nagyobb mint az {sz2}");
else if (sz1 == sz2) Console.WriteLine($"a(z) {sz1} egyenlő a(z){sz2}");
else Console.WriteLine($"a {sz2} nagyobb mint az {sz1}");

Console.WriteLine((sz1 > sz2)? $"a {sz1} nagyobb mint az {sz2}": (sz1 == sz2)? $"a(z) {sz1} egyenlő a(z){sz2}": $"a {sz2} nagyobb mint az {sz1}");


/*
 Egy véletlen számot [1,10], nézzük meg h páros lett-e vagy práratlan 
amit generált
 */
Random random2 = new Random();
int x = random2.Next(10) + 1;
Console.WriteLine((x % 2 == 0) ? "páros" : "páratlan");

/*
 Írjon egy programot, mely egy hármszög oldalainak hosszát [1,20] generálja le,
jelenítsük meg a generált értékeket!És monduk meg h a hármoszög szerkeszthető-e! 
(egy hármoszög szerkeszthtő, ha az (a+b>c) és (a+c>b) és (b+c>a) teljesül)
 */

Random random3 = new Random();

int a = random3.Next(20) + 1;
int b = random3.Next(20) + 1;
int c = random3.Next(20) + 1;

Console.WriteLine(a);
Console.WriteLine(b);
Console.WriteLine(c);

if ((a + b > c) &&(a + c > b) &&(b + c > a)) Console.WriteLine("szerkesztheto a haromszog");
else Console.WriteLine("nem szerkesztheto a haromszog");

Console.WriteLine((a + b > c) && (a + c > b) && (b + c > a)? "szerkesztheto a haromszog": "nem szerkesztheto a haromszog");

/*
 generáljunk egy random értéket -50, 100 között, 
és döntse el a program
hogy a generált szám az -30 és 40 között van-e 
 */

Random random4 = new Random();
int n = random4.Next(151)-50 ;

if (n > -30 && n < 40) Console.WriteLine("A generált szám a két szám között van");
else Console.WriteLine("A generált szám nem az intervallumban van");


Console.WriteLine((n > -30 && n < 40)? "A generált szám a két szám között van": "A generált szám nem az intervallumban van");

int num1 = 12;
int num2 = 10;

//-----------------------------------------------------------------
//értékcsere
int temp = num1;
num1 = num2;
num2 = temp;
```