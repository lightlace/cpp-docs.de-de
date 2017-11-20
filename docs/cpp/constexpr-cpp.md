---
title: Constexpr (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: constexpr_cpp
dev_langs: C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4ff111b73d81fd3c008e53db0f5e41b82f9e3753
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="constexpr-c"></a>constexpr (C++)
Das Schlüsselwort `constexpr` wurde in C++11 eingeführt und in C++14 verbessert. Es bedeutet *Konstantenausdruck*. Wie `const` kann es auf Variablen angewendet werden, sodass ein Compilerfehler ausgelöst wird, wenn der Code versucht, den Wert zu ändern. Im Gegensatz zu `const` kann `constexpr` auch auf Funktionen und Klassenkonstruktoren angewendet werden. `constexpr` gibt an, dass der Wert oder der Rückgabewert eine Konstante ist und nach Möglichkeit zur Kompilierungszeit berechnet wird.  Ein ganzzahliger `constexpr`-Wert kann verwendet werden, wenn eine ganzzahlige Konstante erforderlich ist, wie z. B. in Vorlagenargumenten und Arraydeklarationen. Und wenn ein Wert zur Kompilierzeit statt zur Laufzeit berechnet werden kann, können sie das Programm schneller ausgeführt und belegen weniger Arbeitsspeicher.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);  
```  
  
#### <a name="parameters"></a>Parameter  
 `params`  
 Ein oder mehrere Parameter, die ein Literaltyp (siehe unten) und selbst ein konstanter Ausdruck sein müssen.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine constexpr-Variable oder -Funktion muss einen der Literaltypen zurückgeben, wie unten aufgeführt.  
  
## <a name="literal-types"></a>Literaltypen  
 Um die Komplexität der Berechnungskonstanten zur Kompilierungszeit und deren möglichen Auswirkungen auf die Kompilierungszeit zu beschränken, erfordert der C++14-Standard, dass die an konstanten Ausdrücken beteiligten Typen auf Literaltypen beschränkt werden. Das Layout eines Literaltyps kann zur Kompilierzeit bestimmt werden. Folgende Typen sind Literaltypen:  
  
1.  void  
  
2.  Skalare Typen  
  
3.  Referenzen  
  
4.  Void-Arrays, skalare Typen oder Verweise  
  
5.  Eine Klasse, die einen trivialen Destruktor und einen oder mehrere constexpr-Konstruktoren aufweist, die keine Konstruktoren zum Verschieben oder Kopieren sind. Darüber hinaus müssen alle nicht statischen Datenmember und Basisklassen Literaltypen und permanent sein.  
  
## <a name="constexpr-variables"></a>constexpr-Variablen  
 Der Hauptunterschied zwischen const- und constexpr-Variablen besteht darin, dass die Initialisierung einer const-Variablen bis zur Laufzeit verzögert werden kann, während eine constexpr-Variable zum Zeitpunkt der Kompilierung initialisiert werden muss.  Alle constexpr-Variablen sind auch const.  

-  Eine Variable kann mit `constexpr` deklariert werden, wenn sie über einen Literaltyp verfügt und initialisiert wird. Wenn die Initialisierung von einem Konstruktor ausgeführt wird, muss der Konstruktor als `constexpr` deklariert werden.  
  
-   Ein Verweis kann als constexpr deklariert werden, wenn das Objekt, auf das er verweist, durch einen konstanten Ausdruck initialisiert wurde und alle impliziten Konvertierungen, die während der Initialisierung aufgerufen werden, auch konstante Ausdrücke sind.  
  
-   Alle Deklarationen einer `constexpr`-Variablen oder -Funktion müssen den `constexpr`-Bezeichner haben.  
  
 
  
 
  
```cpp  
constexpr float x = 42.0;  
constexpr float y{108};  
constexpr float z = exp(5, 3);  
constexpr int i; // Error! Not initialized  
int j = 0;  
constexpr int k = j + 1; //Error! j not a constant expression  
```  
  
## <a name="constexpr-functions"></a>constexpr-Funktionen  
 Ein `constexpr`-Funktion ist eine Funktion, deren Rückgabewert zur Kompilierzeit berechnet werden, wenn er vom verwendenden Code benötigt wird.  Wenn die Argumente `constexpr`-Werte sind und der verwendete Code den Rückgabewert zum Zeitpunkt der Kompilierung benötigt, z. B. zum Initialisieren einer `constexpr`-Variable oder zum Bereitstellen eines typlosen Vorlagenarguments, wird eine Kompilierzeitkonstante erzeugt. Bei einem Aufruf mit Nicht-`constexpr`-Argumenten, oder wenn der Wert nicht zum Zeitpunkt der Kompilierung erforderlich ist, wird ein Wert zur Laufzeit wie eine reguläre Funktion erzeugt.  (Durch dieses duale Verhalten müssen Sie keine `constexpr`- und Nicht-`constexpr`-Versionen derselben Funktion schreiben.)  
 
 Ein `constexpr`-Funktion oder ein entsprechender Konstruktor ist implizit `inline`. 
 
 Die folgenden Regeln gelten für Constexpr-Funktionen:

- Ein `constexpr`-Funktion muss Literaltypen akzeptieren und nur Literaltypen zurückgeben. 

- Ein `constexpr`-Funktion kann rekursiv sein. 

- Er darf nicht [virtuellen](../cpp/virtual-cpp.md). Ein Konstruktor kann nicht als Constexpr definiert werden, wenn die einschließende Klasse über virtuellen Basisklassen verfügt über.

- Der Text kann als `= default` oder `= delete` definiert werden. 

- Der Text darf nicht `goto` Anweisungen oder Try-Blöcke. 

- Eine explizite Spezialisierung einer Nicht-constexpr-Vorlage kann als `constexpr` deklariert werden:  
  
- Eine explizite Spezialisierung einer `constexpr`-Vorlage muss nicht auch `constexpr` sein: 


<!--conformance note-->
Die folgenden Regeln gelten für Constexpr-Funktionen in Visual Studio 2017 und höher: 

- Es kann enthalten, wenn und switch-Anweisungen und alle Tabellenschleife-Anweisungen, z. B. für bereichsbasierte, beim, und führen-während
    
- Deklarationen von lokale Variable kann enthalten, aber die Variable muss initialisiert werden, muss ein literal sein und darf nicht statisch oder Thread-lokal sein. Die lokal deklarierte Variable muss nicht konstant sein und möglicherweise geändert wird.

- Eine Constexpr nicht statische Memberfunktion ist nicht erforderlich, um implizit konstant sein.

  
```cpp  
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
```  
  
> [!TIP]
>  Hinweis: Im Visual Studio-Debugger können Sie ermitteln, ob eine `constexpr`-Funktion zur Kompilierzeit ausgewertet wird, indem Sie einen Haltepunkt einfügen. Wenn der Haltepunkt erreicht wird, wurde die Funktion zur Laufzeit aufgerufen.  Wenn dies nicht der Fall ist, wurde die Funktion zum Zeitpunkt der Kompilierung aufgerufen.  
  
 
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt `constexpr`-Variablen, -Funktionen und einen benutzerdefinierten Typ. Beachten Sie, dass in der letzten Anweisung in „main()“ die `constexpr`-Memberfunktion „GetValue()“ einen Aufruf zur Laufzeit darstellt, da der Wert zum Zeitpunkt der Kompilierung nicht bekannt sein muss.  
  
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
  
## <a name="requirements"></a>Anforderungen  
 Visual Studio 2015  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)   
 [const](../cpp/const-cpp.md)