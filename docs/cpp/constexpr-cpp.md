---
title: "constexpr (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "constexpr"
  - "constexpr_cpp"
dev_langs: 
  - "C++"
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# constexpr (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Schlüsselwort `constexpr` wurde in C\+\+11 eingeführt und in C\+\+14 verbessert.  Es bedeutet *konstanter Ausdruck*.  Wie `const` kann es auf Variablen angewendet werden, sodass ein Compilerfehler ausgelöst wird, wenn der Code versucht, den Wert zu ändern.  Im Gegensatz zu `const` kann `constexpr` auch auf Funktionen und Klassenkonstruktoren angewendet werden.  `constexpr` gibt an, dass der Wert oder der Rückgabewert eine Konstante ist und nach Möglichkeit zur Kompilierungszeit berechnet wird.  Ein ganzzahliger `constexpr`\-Wert kann verwendet werden, wenn eine ganzzahlige Konstante erforderlich ist, wie z. B. in Vorlagenargumenten und Arraydeklarationen.  Und wenn ein Wert zur Kompilierzeit statt zur Laufzeit berechnet werden kann, werden dadurch Programme schneller ausgeführt und belegen weniger Speicher.  
  
## Syntax  
  
```vb  
  
constexpr  literal-type  identifier = constant-expression;  
constexpr  literal-type  identifier { constant-expression };  
constexpr literal-type identifier(params );  
constexpr ctor (params);  
```  
  
#### Parameter  
 `params`  
 Ein oder mehrere Parameter, die ein Literaltyp \(siehe unten\) und selbst ein konstanter Ausdruck sein müssen.  
  
## Rückgabewert  
 Eine constexpr\-Variable oder \-Funktion muss einen der Literaltypen zurückgeben, wie unten aufgeführt.  
  
## Literaltypen  
 Um die Komplexität der Berechnungskonstanten zur Kompilierungszeit und deren möglichen Auswirkungen auf die Kompilierungszeit zu beschränken, erfordert der C\+\+14\-Standard, dass die an konstanten Ausdrücken beteiligten Typen auf Literaltypen beschränkt werden.  Das Layout eines Literaltyps kann zur Kompilierzeit bestimmt werden.  Folgende Typen sind Literaltypen:  
  
1.  void  
  
2.  Skalare Typen  
  
3.  Referenzen  
  
4.  Void\-Arrays, skalare Typen oder Verweise  
  
5.  Eine Klasse, die einen trivialen Destruktor und einen oder mehrere constexpr\-Konstruktoren aufweist, die keine Konstruktoren zum Verschieben oder Kopieren sind.  Darüber hinaus müssen alle nicht statischen Datenmember und Basisklassen Literaltypen und permanent sein.  
  
## constexpr\-Variablen  
 Der Hauptunterschied zwischen const\- und constexpr\-Variablen besteht darin, dass die Initialisierung einer const\-Variablen bis zur Laufzeit verzögert werden kann, während eine constexpr\-Variable zum Zeitpunkt der Kompilierung initialisiert werden muss.  Alle constexpr\-Variablen sind auch const.  
  
```  
constexpr float x = 42.0;  
constexpr float y{108};  
constexpr float z = exp(5, 3);  
constexpr int i; // Error! Not initialized  
int j = 0;  
constexpr int k = j + 1; //Error! j not a constant expression  
```  
  
## constexpr\-Funktionen  
 Ein `constexpr`\-Funktion ist eine Funktion, deren Rückgabewert zur Kompilierzeit berechnet werden, wenn er vom verwendenden Code benötigt wird.  Ein `constexpr`\-Funktion muss Literaltypen akzeptieren und nur Literaltypen zurückgeben.  Wenn die Argumente `constexpr`\-Werte sind und der verwendete Code den Rückgabewert zum Zeitpunkt der Kompilierung benötigt, z. B. zum Initialisieren einer `constexpr`\-Variable oder zum Bereitstellen eines typlosen Vorlagenarguments, wird eine Kompilierzeitkonstante erzeugt.  Bei einem Aufruf mit Nicht\-`constexpr`\-Argumenten, oder wenn der Wert nicht zum Zeitpunkt der Kompilierung erforderlich ist, wird ein Wert zur Laufzeit wie eine reguläre Funktion erzeugt.  \(Durch dieses duale Verhalten müssen Sie keine `constexpr`\- und Nicht\-`constexpr`\-Versionen derselben Funktion schreiben.\)  
  
```  
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
```  
  
> [!TIP]
>  Hinweis: Im Visual Studio\-Debugger können Sie ermitteln, ob eine `constexpr`\-Funktion zur Kompilierzeit ausgewertet wird, indem Sie einen Haltepunkt einfügen.  Wenn der Haltepunkt erreicht wird, wurde die Funktion zur Laufzeit aufgerufen.  Wenn dies nicht der Fall ist, wurde die Funktion zum Zeitpunkt der Kompilierung aufgerufen.  
  
## Allgemeine constexpr\-Regeln  
 Für eine Funktion, eine Variable, einen Konstruktor oder einen statischen Datenmember, die bzw. der als `constexpr` definiert werden soll, müssen bestimmte Anforderungen erfüllt werden:  
  
-   Ein `constexpr`\-Funktion kann rekursiv sein.  Sie darf nicht [virtuell](../cpp/virtual-cpp.md) sein, und der Rückgabetyp und die Parametertypen müssen Literaltypen sein.  Der Text kann als `= default` oder `= delete` definiert werden.  Andernfalls muss er diesen Regeln entsprechen: Er enthält keine `goto`\-Anweisungen, Try\-Blöcke, nicht initialisierte Variablen oder Variablendefinitionen, die keine Literaltypen sind oder die statisch oder Thread\-lokal sind.  Darüber hinaus darf ein Konstruktor nicht als constexpr definiert werden, wenn die einschließende Klasse über virtuelle Basisklassen verfügt.  
  
-   Eine Variable kann mit `constexpr` deklariert werden, wenn sie über einen Literaltyp verfügt und initialisiert wird.  Wenn die Initialisierung von einem Konstruktor ausgeführt wird, muss der Konstruktor als `constexpr` deklariert werden.  
  
-   Ein Verweis kann als constexpr deklariert werden, wenn das Objekt, auf das er verweist, durch einen konstanten Ausdruck initialisiert wurde und alle impliziten Konvertierungen, die während der Initialisierung aufgerufen werden, auch konstante Ausdrücke sind.  
  
-   Alle Deklarationen einer `constexpr`\-Variablen oder \-Funktion müssen den `constexpr`\-Bezeichner haben.  
  
-   Eine explizite Spezialisierung einer Nicht\-constexpr\-Vorlage kann als `constexpr` deklariert werden:  
  
-   Eine explizite Spezialisierung einer `constexpr`\-Vorlage muss nicht auch `constexpr` sein:  
  
-   Ein `constexpr`\-Funktion oder ein entsprechender Konstruktor ist implizit `inline`.  
  
## Beispiel  
 Das folgende Beispiel zeigt `constexpr`\-Variablen, \-Funktionen und einen benutzerdefinierten Typ.  Beachten Sie, dass in der letzten Anweisung in „main\(\)“ die `constexpr`\-Memberfunktion „GetValue\(\)“ einen Aufruf zur Laufzeit darstellt, da der Wert zum Zeitpunkt der Kompilierung nicht bekannt sein muss.  
  
```  
#include <iostream>  
  
using namespace std;  
  
// Pass by value   
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
  
// Pass by reference  
constexpr float exp2(const float& x, const int& n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp2(x * x, n / 2) :  
        exp2(x * x, (n - 1) / 2) * x;  
};  
  
// Compile time computation of array length  
template<typename T, int N>  
constexpr int length(const T(&ary)[N])   
{   
    return N;   
}   
  
// Recursive constexpr function  
constexpr int fac(int n)  
{   
    return n == 1 ? 1 : n*fac(n - 1);   
}  
  
// User-defined type  
class Foo  
{  
public:  
    constexpr explicit Foo(int i) : _i(i) {}  
    constexpr int GetValue()  
    {  
        return _i;  
    }  
private:  
    int _i;  
};  
  
int main()  
{  
    //foo is const:  
    constexpr Foo foo(5);   
    // foo = Foo(6); //Error!  
  
    //Compile time:  
    constexpr float x = exp(5, 3);   
    constexpr float y { exp(2, 5) };  
    constexpr int val = foo.GetValue();   
    constexpr int f5 = fac(5);  
    const int nums[] { 1, 2, 3, 4 };  
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };  
  
    //Run time:   
    cout << "The value of foo is " << foo.GetValue() << endl;   
  
}  
  
```  
  
## Anforderungen  
 Visual Studio 2015  
  
## Siehe auch  
 [Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)   
 [const](../cpp/constexpr-cpp.md)