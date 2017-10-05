---
title: "Funktionsüberladung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function overloading, about function overloading
- function overloading
- declaring functions, overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9076fdd48e466d68d5dcecec2c339a98f39a8bb1
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="function-overloading"></a>Funktionsüberladung
C++ lässt die Angabe mehrerer Funktionen mit dem gleichen Namen im gleichen Gültigkeitsbereich zu. Diese werden als überladene Funktionen bezeichnet und ausführlich unter "Überladen" beschrieben. Überladene Funktionen ermöglichen Programmierern das Bereitstellen anderer Semantiken für eine Funktion in Abhängigkeit von den Typen und der Anzahl von Argumenten.  
  
 Z. B. eine **Drucken** Funktion, die eine Zeichenfolge akzeptiert (oder **Char \* **) Argument führt sehr unterschiedliche Aufgaben als eine, die ein Argument des Typs **doppelte** . Das Überladen ermöglicht eine einheitliche Benennung und verhindert, dass Programmierer Namen wie `print_sz` oder `print_d` erfinden müssen. Die folgende Tabelle zeigt, welche Teile einer Funktionsdeklaration von C++ verwendet werden, um zwischen Gruppen von Funktionen mit dem gleichen Namen und dem gleichen Gültigkeitsbereich zu differenzieren.  
  
### <a name="overloading-considerations"></a>Überlegungen zur Überladung  
  
|Funktionsdeklarationselement|Wird zum Überladen verwendet?|  
|----------------------------------|---------------------------|  
|Funktionsrückgabetyp|Nein|  
|Anzahl der Argumente|Ja|  
|Typ der Argumente|Ja|  
|Vorhandensein oder Abwesenheit von Auslassungszeichen|Ja|  
|Verwendung von `typedef`-Namen|Nein|  
|Nicht angegebene Arraygrenzen|Nein|  
|**const** oder `volatile` (siehe unten)|Ja|  
  
 Obwohl Funktionen auf Grundlage des Rückgabetyps unterschieden werden können, können sie nicht auf dieser Grundlage überladen werden.  `Const`oder `volatile` dienen nur als Grundlage zum Überladen, wenn sie in einer Klasse verwendet werden, zum Anwenden der **dies** Zeiger für die Klasse, die nicht den Rückgabetyp der Funktion.  Das heißt, Überladung gilt nur, wenn die **const** oder `volatile` Schlüsselwort folgt Argumentliste der Funktion in der Deklaration.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie das Überladen verwendet werden kann.  
  
```  
// function_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <math.h>  
  
// Prototype three print functions.  
int print( char *s );                  // Print a string.  
int print( double dvalue );            // Print a double.  
int print( double dvalue, int prec );  // Print a double with a  
//  given precision.  
using namespace std;  
int main( int argc, char *argv[] )  
{  
const double d = 893094.2987;  
if( argc < 2 )  
    {  
// These calls to print invoke print( char *s ).  
print( "This program requires one argument." );  
print( "The argument specifies the number of" );  
print( "digits precision for the second number" );  
print( "printed." );  
exit(0);  
    }  
  
// Invoke print( double dvalue ).  
print( d );  
  
// Invoke print( double dvalue, int prec ).  
print( d, atoi( argv[1] ) );  
}  
  
// Print a string.  
int print( char *s )  
{  
cout << s << endl;  
return cout.good();  
}  
  
// Print a double in default precision.  
int print( double dvalue )  
{  
cout << dvalue << endl;  
return cout.good();  
}  
  
// Print a double in specified precision.  
//  Positive numbers for precision indicate how many digits  
//  precision after the decimal point to show. Negative  
//  numbers for precision indicate where to round the number  
//  to the left of the decimal point.  
int print( double dvalue, int prec )  
{  
// Use table-lookup for rounding/truncation.  
static const double rgPow10[] = {   
10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,  
10E1,  10E2,  10E3,  10E4, 10E5,  10E6  
    };  
const int iPowZero = 6;  
// If precision out of range, just print the number.  
if( prec < -6 || prec > 7 )  
return print( dvalue );  
// Scale, truncate, then rescale.  
dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *  
rgPow10[iPowZero - prec];  
cout << dvalue << endl;  
return cout.good();  
}  
```  
  
 Der vorhergehende Code zeigt das Überladen der `print`-Funktion im Dateigültigkeitsbereich an.  
  
 Das Standardargument wird nicht als Teil des Funktionstyps betrachtet. Daher erfolgt keine Verwendung beim Auswählen überladener Funktionen. Zwei Funktionen, die sich nur bei den Standardargumenten unterscheiden, werden als mehrfache Definitionen und nicht als überladene Funktionen betrachtet.  
  
 Standardargumente können nicht für überladene Operatoren angegeben werden.  
  
  
## <a name="argument-matching"></a>Argumentübereinstimmung  
 Überladene Funktionen werden für die beste Übereinstimmung von Funktionsdeklarationen im aktuellen Bereich für Argumente ausgewählt, die im Funktionsaufruf angegeben werden. Wenn eine passende Funktion gefunden wird, wird diese Funktion aufgerufen. "Passend" in diesem Kontext bedeutet Folgendes:  
  
-   Ein exakte Übereinstimmung wurde gefunden.  
  
-   Eine triviale Konvertierung wurde ausgeführt.  
  
-   Eine ganzzahlige Heraufstufung wurde ausgeführt.  
  
-   Eine Standardkonvertierung zum gewünschten Argumenttyp ist vorhanden.  
  
-   Eine benutzerdefinierte Konvertierung (entweder Konvertierungsoperator oder Konstruktor) auf den gewünschten Argumenttyp ist vorhanden.  
  
-   Es wurden durch Ellipsen dargestellte Argumente gefunden.  
  
 Der Compiler erstellt einen Satz Kandidatenfunktionen für jedes Argument. Kandidatenfunktionen sind Funktionen, in denen das tatsächliche Argument an dieser Position in den Typ des formalen Arguments konvertiert werden kann.  
  
 Ein Satz von "am besten passenden Funktionen" wird für jedes Argument erstellt, und die ausgewählte Funktion ist die Schnittmenge aller Sätze. Wenn die Schnittmenge mehr als eine Funktion enthält, ist das Überladen mehrdeutig und generiert einen Fehler. Die letztendlich ausgewählte Funktion stimmt stets besser überein als jede andere Funktion in der Gruppe für mindestens ein Argument. Wenn dies nicht der Fall ist (wenn kein klarer Gewinner vorhanden ist), generiert der Funktionsaufruf einen Fehler.  
  
 Berücksichtigen Sie die folgenden Deklarationen (Funktionen sind zur Identifikation der folgenden Erläuterung als `Variant 1`, `Variant 2` und `Variant 3` gekennzeichnet):  
  
```  
Fraction &Add( Fraction &f, long l );       // Variant 1  
Fraction &Add( long l, Fraction &f );       // Variant 2  
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3  
  
Fraction F1, F2;  
```  
  
 Betrachten Sie folgende Anweisung:  
  
```  
F1 = Add( F2, 23 );  
```  
  
 Die vorhergehende Anweisung erstellt zwei Sätze:  
  
|Satz 1: Kandidatenfunktionen, deren erstes Argument vom Typ "fraction" ist|Satz 2: Kandidatenfunktionen, deren zweites Argument in den Typ "int" konvertiert werden kann|  
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|Variant 1|Variant 1 (`int` kann in `long` mithilfe einer Standardkonvertierung konvertiert werden)|  
|Variant 3||  
  
 Funktionen in Satz 2 sind Funktionen, für die es implizite Konvertierungen vom tatsächlichen Parametertyp in den formalen Parametertyp gibt. Unter diesen Funktionen gibt es eine Funktion mit den geringsten "Kosten" für die Konvertierung des tatsächlichen Parametertyps in den formalen Parametertyp.  
  
 Die Schnittmenge dieser beiden Sätze ist "Variant 1". Ein Beispiel für einen mehrdeutigen Funktionsaufruf ist:  
  
```  
F1 = Add( 3, 6 );  
```  
  
 Der vorhergehende Funktionsaufruf erstellt die folgenden Sätze:  
  
|Satz 1: Kandidatenfunktionen, deren erstes Argument vom Typ "int" ist|Satz 2: Kandidatenfunktionen, deren zweites Argument vom Typ "int" ist|  
|---------------------------------------------------------------------|----------------------------------------------------------------------|  
|Variant 2 (`int` kann in `long` mithilfe einer Standardkonvertierung konvertiert werden)|Variant 1 (`int` kann in `long` mithilfe einer Standardkonvertierung konvertiert werden)|  
  
 Beachten Sie, dass die Schnittmenge zwischen diesen beiden Sätzen leer ist. Aus diesem Grund generiert der Compiler eine Fehlermeldung.  
  
 Für die argumentübereinstimmung wird eine Funktion mit * n * Standardargumente so behandelt, als * n *+ 1 unterschiedliche Funktionen, jeweils mit einer anderen Anzahl von Argumenten.  
  
 Die Ellipse (...) dient als Platzhalter; sie stimmt mit jedem tatsächlichen Argument überein. Dies kann zu vielen mehrdeutigen Gruppen führen, wenn Sie die überladene Funktion nicht mit größter Sorgfalt entwerfen.  
  
> [!NOTE]
>  Mehrdeutigkeit von überladenen Funktionen kann nicht bestimmt werden, bis ein Funktionsaufruf gefunden wird. An diesem Punkt werden die Sätze für jedes Argument im Funktionsaufruf erstellt, und Sie können bestimmen, ob eine eindeutige Überladung vorhanden ist. Dies bedeutet, dass Mehrdeutigkeiten im Code vorhanden sein dürfen, bis sie durch einen bestimmten Funktionsaufruf eindeutig deklariert werden.  
  
## <a name="argument-type-differences"></a>Unterschiede bei Argumenttypen  
 Überladene Funktionen unterscheiden zwischen Argumenttypen, die verschiedene Initialisierer erfordern. Daher gelten ein Argument eines angegebenen Typs und ein Verweis auf diesen Typ für den Zweck des Überladens als identisch. Sie gelten als identisch, weil sie die gleichen Initialisierer erfordern. `max( double, double )` wird beispielsweise identisch mit `max( double &, double & )` betrachtet. Das Deklarieren von zwei solcher Funktionen verursacht einen Fehler.  
  
 Aus demselben Grund Funktionsargumente eines Typs, die geändert, indem **const** oder `volatile` sind nicht anders behandelt als der Basistyp für den Zweck des Überladens.  
  
 Allerdings kann die Funktion überladen Mechanismus zwischen verweisen, die durch qualifiziert sind unterscheiden **const** und `volatile` und Verweise auf den Basistyp. Dies ermöglicht Code wie den folgenden:  
  
```  
// argument_type_differences.cpp  
// compile with: /EHsc /W3  
// C4521 expected  
#include <iostream>  
  
using namespace std;  
class Over {  
public:  
   Over() { cout << "Over default constructor\n"; }  
   Over( Over &o ) { cout << "Over&\n"; }  
   Over( const Over &co ) { cout << "const Over&\n"; }  
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }  
};  
  
int main() {  
   Over o1;            // Calls default constructor.  
   Over o2( o1 );      // Calls Over( Over& ).  
   const Over o3;      // Calls default constructor.  
   Over o4( o3 );      // Calls Over( const Over& ).  
   volatile Over o5;   // Calls default constructor.  
   Over o6( o5 );      // Calls Over( volatile Over& ).  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Over default constructor  
Over&  
Over default constructor  
const Over&  
Over default constructor  
volatile Over&  
```  
  
 Zeiger auf **const** und `volatile` -Objekte gelten auch als Zeiger auf den Basistyp unterscheiden für den Zweck des Überladens.  
  
## <a name="argument-matching-and-conversions"></a>Argumentübereinstimmung und Konvertierungen  
 Wenn der Compiler versucht, die tatsächlichen Argumente mit den Argumenten in Funktionsdeklarationen abzugleichen, kann er Standardkonvertierungen oder benutzerdefinierte Konvertierungen bereitstellen, um den korrekten Typ zu erhalten, wenn keine genaue Übereinstimmung gefunden wird. Die Anwendung von Konvertierungen unterliegt diesen Regeln:  
  
-   Sequenzen von Konvertierungen, die mehr als eine benutzerdefinierte Konvertierung enthalten, werden nicht berücksichtigt.  
  
-   Sequenzen von Konvertierungen, die gekürzt werden können, indem Konvertierungen im Zwischenformat entfernt werden, werden nicht berücksichtigt.  
  
 Das Ergebnis der Konvertierungssequenz, falls vorhanden, ist die am besten passende Sequenz. Es gibt mehrere Möglichkeiten, ein Objekt vom Typ konvertieren `int` Eingabe `unsigned long` mithilfe von standardkonvertierungen (beschrieben [Standardkonvertierungen](../cpp/standard-conversions.md)):  
  
-   Konvertieren von `int` in `long` und dann von `long` in `unsigned long`.  
  
-   Konvertieren von `int` in `unsigned long`.  
  
 Auch wenn die erste Sequenz das erwünschte Ziel erreicht, ist sie nicht die Sequenz mit der stärksten Übereinstimmung – es gibt eine kürzere Sequenz.  
  
 Die folgende Tabelle zeigt eine Gruppe von Konvertierungen, die als triviale Konvertierungen bezeichnet werden, die eine begrenzte Auswirkung auf die Bestimmung haben, welche Sequenz die größte Übereinstimmung hat. Die Instanzen, in denen triviale Konvertierungen sich auf die Sequenzwahl auswirken, werden in der Liste nach der Tabelle behandelt.  
  
### <a name="trivial-conversions"></a>Triviale Konvertierungen  
  
|Konvertieren von Typ|Konvertiert in Typ|  
|-----------------------|---------------------|  
|*Typname*|*Typname***&**|  
|*Typname***&**|*Typname*|  
|*Typname* **]**|*Typname\**|  
|*Typname* **(** *Argumentliste* **)**|**(** * \*Typname* **) (** *Argumentliste* **)**|  
|*Typname*|**const** *Typname*|  
|*Typname*|`volatile`*Typname*|  
|*Typname\**|**const** *Typname\**|  
|*Typname\**|`volatile`*Typname\**|  
  
 Die Reihenfolge für Konvertierungen lautet wie folgt:  
  
1.  Genaue Übereinstimmung. Ein genaue Übereinstimmung zwischen den Typen, mit denen die Funktion aufgerufen wird und den Typen, die im Funktionsprototyp deklariert werden, ist immer die beste Übereinstimmung. Sequenzen von trivialen Konvertierungen werden als exakte Übereinstimmungen klassifiziert. Allerdings sind Sequenzen, die keine dieser Konvertierungen ausführen, besser als Sequenzen, die konvertieren:  
  
    -   Von Zeiger in Zeiger auf **const** (`type` ** \* ** auf **const** `type` ** \* ** ).  
  
    -   Von Zeiger in Zeiger auf `volatile` (`type` ** \* ** auf `volatile` `type` ** \* **).  
  
    -   Von Verweis in Verweis auf **const** (`type` ** & ** auf **const** `type` ** & **).  
  
    -   Von Verweis in Verweis auf `volatile` (`type` ** & ** auf `volatile` `type` ** & **).  
  
2.  Übereinstimmung mithilfe von Erweiterungen. Jede beliebige Sequenz nicht als genaue Übereinstimmung, die nur ganzzahlige Erweiterungen, Konvertierungen von enthält klassifiziert **"float"** auf **doppelte**, und triviale Konvertierungen wird als Übereinstimmung mithilfe von Erweiterungen klassifiziert. Obwohl eine Übereinstimmung mit Erweiterungen besser ist als eine Übereinstimmung, die Standardkonvertierungen verwendet, ist sie nicht so gut wie eine genaue Übereinstimmung.  
  
3.  Übereinstimmung mithilfe von Standardkonvertierungen. Jede beliebige Sequenz, die nicht als genaue Übereinstimmung klassifiziert wird, oder eine Übereinstimmung mithilfe von Erweiterungen, die nur Standardkonvertierungen und triviale Konvertierungen enthält, wird als Übereinstimmung mithilfe von Standardkonvertierungen klassifiziert. In dieser Kategorie gelten die folgenden Regeln:  
  
    -   Konvertierung von einem Zeiger auf eine abgeleitete Klasse, um einen Zeiger auf eine direkte oder indirekte Basisklasse ist für die Konvertierung zu vorzuziehen **"void" \* ** oder **const "void" \* **.  
  
    -   Die Konvertierung von einem Zeiger auf eine abgeleitete Klasse in einen Zeiger auf eine Basisklasse erzeugt eine bessere Übereinstimmung, je näher die Basisklasse der direkten Basisklasse ist. Angenommen, die Klassenhierarchie folgt der in der folgenden Abbildung dargestellten Klassenhierarchie.  
  
 ![Bevorzugte Konvertierungen](../cpp/media/vc391t1.gif "vc391T1")  
Diagramm zur Veranschaulichung bevorzugter Konvertierungen  
  
 Die Konvertierung von Typ `D*` in Typ `C*` ist der Konvertierung von Typ `D*` in Typ `B*` vorzuziehen. Entsprechend ist die Konvertierung von Typ `D*` in Typ `B*` der Konvertierung von Typ `D*` in Typ `A*` vorzuziehen.  
  
 Die gleiche Regel gilt für Verweiskonvertierungen. Die Konvertierung von Typ `D&` in Typ `C&` ist der Konvertierung von Typ `D&` in Typ `B&` usw. vorzuziehen.  
  
 Die gleiche Regel gilt für pointer-to-member-Konvertierungen. Die Konvertierung von Typ `T D::*` in Typ `T C::*` ist der Konvertierung von Typ `T D::*` in Typ `T B::*` und so weiter vorzuziehen (wobei `T` der Typ des Members ist).  
  
 Die vorhergehende Regel gilt nur für einen bestimmten Ableitungspfad. Betrachten Sie das Diagramm, das in der folgenden Abbildung dargestellt wird.  
  
 ![Mehrere &#45; Vererbung mit bevorzugten Konvertierungen](../cpp/media/vc391t2.gif "vc391T2")  
Mehrfachvererbungsdiagramm zur Veranschaulichung bevorzugter Konvertierungen  
  
 Die Konvertierung von Typ `C*` in Typ `B*` ist der Konvertierung von Typ `C*` in Typ `A*` vorzuziehen. Der Grund liegt darin, dass sie sich auf dem gleichen Pfad befinden, und `B*` näher liegt. Allerdings ist die Konvertierung von Typ `C*` in Typ `D*` der Konvertierung in Typ `A*` nicht vorzuziehen. Keiner der Typen hat Vorrang gegenüber dem anderen, da die Konvertierungen verschiedenen Pfaden folgen.  
  
1.  Übereinstimmung mit benutzerdefinierten Konvertierungen. Diese Sequenz kann nicht als genaue Übereinstimmung, als Übereinstimmung mithilfe von Erweiterungen oder als Übereinstimmung mithilfe von Standardkonvertierungen klassifiziert werden. Die Reihenfolge darf nur benutzerdefinierte Konvertierungen, Standardkonvertierungen oder triviale Konvertierungen enthalten, um die Übereinstimmung mit benutzerdefinierten Konvertierungen zu erreichen. Eine Übereinstimmung mit benutzerdefinierten Konvertierungen gilt als eine bessere Übereinstimmung als eine Übereinstimmung mit einem Auslassungszeichen, jedoch als nicht so gut wie eine Übereinstimmung mit Standardkonvertierungen.  
  
2.  Übereinstimmung mit einem Auslassungszeichen. Jede beliebige Sequenz, die Auslassungszeichen in der Deklaration entspricht, wird als Übereinstimmung mit einem Auslassungszeichen klassifiziert. Dies wird als schwächste Übereinstimmung angesehen.  
  
 Benutzerdefinierte Konvertierungen werden angewendet, wenn keine integrierte Erweiterung oder Konvertierung vorhanden ist. Diese Konvertierungen werden auf der Grundlage des Typs des Arguments ausgewählt, das abgeglichen wird. Betrachten Sie folgenden Code:  
  
```  
// argument_matching1.cpp  
class UDC  
{  
public:  
   operator int()  
   {  
      return 0;  
   }  
   operator long();  
};  
  
void Print( int i )  
{  
};  
  
UDC udc;  
  
int main()  
{  
   Print( udc );  
}  
```  
  
 Die verfügbaren benutzerdefinierten Konvertierungen für die Klasse `UDC` sind vom Typ `int` und Typ **lang**. Deshalb berücksichtigt der Compiler Konvertierungen für den Typ des Objekts, das abgeglichen wird: `UDC`. Eine Konvertierung in `int` ist vorhanden, und sie ist ausgewählt.  
  
 Während des Prozesseses zum Zuordnen von Argumenten können Standardkonvertierungen sowohl auf das Argument als auch auf das Ergebnis einer benutzerdefinierten Konvertierung angewendet werden. Daher funktioniert der folgende Code:  
  
```  
void LogToFile( long l );  
...  
UDC udc;  
LogToFile( udc );  
```  
  
 Im vorherigen Beispiel, die benutzerdefinierte Konvertierung **Operator long**, wird aufgerufen, um konvertieren `udc` Eingabe **lang**. Wenn keine benutzerdefinierte Konvertierung in Typ **lange** wurde definiert, die Konvertierung würde wie folgt fortgesetzt: Typ `UDC` würde Typ konvertiert wurden `int` mit der eine benutzerdefinierte Konvertierung. Klicken Sie dann die standardkonvertierung vom Typ `int` Eingabe **lange** würden angewendet wurde, um das Argument in der Deklaration entspricht.  
  
 Wenn für die Übereinstimmung mit einem Argument eine benutzerdefinierte Konvertierung erforderlich ist, werden die Standardkonvertierungen bei der Suche nach der besten Übereinstimmung nicht verwendet. Dies gilt auch dann, wenn mehr als eine Kandidatenfunktion eine benutzerdefinierte Konvertierung erfordert. In so einem Fall werden die Funktionen als gleich betrachtet. Zum Beispiel:  
  
```  
// argument_matching2.cpp  
// C2668 expected  
class UDC1  
{  
public:  
   UDC1( int );  // User-defined conversion from int.  
};  
  
class UDC2  
{  
public:  
   UDC2( long ); // User-defined conversion from long.  
};  
  
void Func( UDC1 );  
void Func( UDC2 );  
  
int main()  
{  
   Func( 1 );  
}  
```  
  
 Beide Versionen von `Func` erfordern eine benutzerdefinierte Konvertierung zum Konvertieren des `int`-Typs in das Argument des Klassentyps. Mögliche Konversionen sind:  
  
-   Konvertieren vom Typ `int` in den Typ `UDC1` (eine benutzerdefinierte Konvertierung).  
  
-   Konvertieren vom Typ `int` Eingabe **lange**; anschließende Konvertierung in den Typ `UDC2` (in zwei Schritten-Konvertierung).  
  
 Obwohl es die zweite dieser Konvertierungen eine Standardkonvertierung sowie die benutzerdefinierte Konvertierung erfordert, gelten die zwei Konvertierungen noch immer als gleich.  
  
> [!NOTE]
>  Benutzerdefinierte Konvertierungen gelten als Konvertierung durch Konstruktion oder als Konvertierung durch Initialisierung (Konvertierungsfunktion). Beide Methoden werden als gleich betrachtet, wenn die beste Übereinstimmung berücksichtigt wird.  
  
## <a name="argument-matching-and-the-this-pointer"></a>Argumentübereinstimmung und der this-Zeiger  
 Klassenmemberfunktionen werden unterschiedlich behandelt, je nachdem, ob sie als `static` deklariert werden. Da nicht statische Funktionen über ein implizites Argument verfügen, das den `this`-Zeiger bereitstellt, gelten nicht statische Funktionen als mit einem weiterem Argument ausgestattet als statische Funktionen; andernfalls werden sie genauso deklariert.  
  
 Diese nicht statischen Memberfunktionen erfordern, dass der implizite `this`-Zeiger dem Objekttyp entspricht, über den die Funktion aufgerufen wurde, oder für überladene Operatoren, dass das erste Argument dem Objekt entspricht, auf das der Operator angewendet wird. (Weitere Informationen zu überladenen Operatoren finden Sie unter [überladene Operatoren](../cpp/operator-overloading.md).)  
  
 Im Gegensatz zu anderen Argumenten in überladenen Funktionen werden keine temporären Objekte eingeführt und keine Konvertierungen angestrebt, wenn versucht wird, mit dem `this`-Zeigerargument übereinzustimmen.  
  
 Wenn die `->` Memberauswahloperator wird verwendet, um eine Memberfunktion der Klasse zuzugreifen `class_name`, `this` Zeigerargument weist den `class_name * const`. Wenn die Member, als deklariert werden `const` oder `volatile`, sind die Typen `const class_name * const` und `volatile class_name * const`zugeordnet.  
  
 Der Memberauswahloperator `.` funktioniert genau auf die gleiche Weise, außer dass ein impliziter `&`-Operator (address-of) dem Objektnamen vorangestellt ist. Im folgenden Beispiel wird gezeigt, wie dies funktioniert:  
  
```  
// Expression encountered in code  
obj.name  
  
// How the compiler treats it  
(&obj)->name  
```  
  
 Der linke Operand der Operatoren `->*` und `.*` (Zeiger auf Member) wird hinsichtlich der Argumentübereinstimmung genauso wie der `.`-Operator und der `->`-Operator (Memberauswahl) behandelt.  
  
## <a name="restrictions"></a>Beschränkungen  
 Mehrere Einschränkungen steuern eine akzeptable Gruppe von überladenen Funktionen:  
  
-   Zwei beliebige Funktionen in einer Gruppe von überladenen Funktionen müssen unterschiedliche Argumentlisten haben.  
  
-   Das Überladen von Funktionen mit Argumentlisten der gleichen Typen auf alleiniger Grundlage des Rückgabetyps ist ein Fehler.  
  
     **Microsoft-spezifisch**  
  
 Sie können überladen **new-Operator** einzig auf basis des Rückgabetyp – für Speichermodelle dem Speichermodell Modifizierer angegeben.  
  
**Ende Microsoft-spezifisch**  
  
-   Memberfunktionen können nicht allein auf der Grundlage, dass eine statisch und die andere nicht statisch ist, überladen werden.  
  
-   `typedef`-Deklarationen definieren keine neue Typen. Sie führen Synonyme für vorhandene Typen ein. Sie wirken sich nicht auf den Mechanismus zum Überladen aus. Betrachten Sie folgenden Code:  
  
    ```  
    typedef char * PSTR;  
  
    void Print( char *szToPrint );  
    void Print( PSTR szToPrint );  
    ```  
  
     Die vorhergehenden zwei Funktionen verfügen über identische Argumentlisten. `PSTR`ist ein Synonym für den Typ **Char \* **. Im Memberbereich generiert dieser Code einen Fehler.  
  
-   Aufgelistete Typen sind verschiedene Typen und können verwendet werden, um zwischen überladenen Funktionen zu unterscheiden.  
  
-   Die Typen "Array von" und "Zeiger auf" gelten als identisch, damit zwischen überladenen Funktionen unterschieden werden kann. Dies gilt nur für eindimensionale Arrays. Daher verursachen die folgenden überladenen Funktionen einen Konflikt und generieren eine Fehlermeldung:  
  
    ```  
    void Print( char *szToPrint );  
    void Print( char szToPrint[] );  
    ```  
  
     Für mehrdimensionale Arrays gelten die zweite und alle nachfolgenden Dimensionen als Teil des Typs. Deshalb werden sie beim Unterscheiden zwischen überladenen Funktionen verwendet:  
  
    ```  
    void Print( char szToPrint[] );  
    void Print( char szToPrint[][7] );  
    void Print( char szToPrint[][9][42] );  
    ```  
  
## <a name="declaration-matching"></a>Deklarationsübereinstimmung  
 Zwei beliebige Funktionsdeklarationen des gleichen Namens im gleichen Bereich können auf die gleiche Funktion oder zwei einzelne Funktionen, die überladen werden, verweisen. Wenn die Argumentlisten der Deklarationen Argumente äquivalenter Typen enthalten (wie im vorherigen Abschnitt beschrieben), beziehen sich die Funktionsdeklarationen auf die gleiche Funktion. Andernfalls beziehen sie sich auf zwei separate Funktionen, die mithilfe des Überladens ausgewählt werden.  
  
 Der Klassenbereich wird strikt beachtet. Deshalb befindet sich eine Funktion, die in einer Basisklasse deklariert wurde, nicht im selben Bereich wie eine Funktion, die in einer abgeleiteten Klasse deklariert wurde. Wenn eine Funktion in einer abgeleiteten Klasse mit dem gleichen Namen wie eine Funktion in der Basisklasse deklariert ist, blendet die Funktion der abgeleiteten Klasse die Basisklassenfunktion aus, und es erfolgt keine Überladung.  
  
 Der Blockbereich wird strikt beachtet. Deshalb befindet sich eine Funktion, die im Dateibereich deklariert ist, nicht im selben Bereich wie eine lokal deklarierte Funktion. Wenn eine lokal deklarierte Funktion den gleichen Namen wie eine Funktion besitzt, die im Dateibereich deklariert wird, blendet die lokal deklarierte Funktion die Funktion im Dateibereich aus, und es erfolgt keine Überladung. Zum Beispiel:  
  
```  
// declaration_matching1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void func( int i )  
{  
    cout << "Called file-scoped func : " << i << endl;  
}  
  
void func( char *sz )  
{  
   cout << "Called locally declared func : " << sz << endl;  
}  
  
int main()  
{  
   // Declare func local to main.  
   extern void func( char *sz );  
  
   func( 3 );   // C2664 Error. func( int ) is hidden.  
   func( "s" );  
}  
```  
  
 Der vorhergehende Code zeigt zwei Definitionen der Funktion `func`. Die Definition, die ein Argument vom Typ `char *` akzeptiert, ist gegenüber `main` aufgrund der `extern`-Anweisung lokal vorhanden. Daher wird die Definition, die ein Argument vom Typ `int` akzeptiert, ausgeblendet, und der erste Aufruf von `func` ist fehlerhaft.  
  
 Für überladene Memberfunktionen können verschiedenen Versionen der Funktion unterschiedliche Zugriffsrechte zugewiesen werden. Sie werden weiterhin als im Gültigkeitsbereich der einschließenden Klasse betrachtet und sind somit überladene Funktionen. Betrachten Sie den folgenden Code, in dem die Memberfunktion `Deposit` überladen wird. Eine Version ist öffentlich, die andere privat.  
  
 Der Zweck dieses Beispiels ist es, eine `Account`-Klasse bereitzustellen, in der ein korrektes Kennwort erforderlich ist, um Eingaben vorzunehmen. Dies wird mithilfe der Überladung erreicht.  
  
 Beachten Sie, dass der Aufruf von `Deposit` in `Account::Deposit` die private Memberfunktion aufruft. Dieser Aufruf ist korrekt, da `Account::Deposit` eine Memberfunktion ist und daher Zugriff auf private Member der Klasse hat.  
  
```  
// declaration_matching2.cpp  
class Account  
{  
public:  
   Account()  
   {  
   }  
   double Deposit( double dAmount, char *szPassword );  
  
private:  
   double Deposit( double dAmount )  
   {  
      return 0.0;  
   }  
   int Validate( char *szPassword )  
   {  
      return 0;  
   }  
  
};  
  
int main()  
{  
    // Allocate a new object of type Account.  
    Account *pAcct = new Account;  
  
    // Deposit $57.22. Error: calls a private function.  
    // pAcct->Deposit( 57.22 );  
  
    // Deposit $57.22 and supply a password. OK: calls a  
    //  public function.  
    pAcct->Deposit( 52.77, "pswd" );  
}  
  
double Account::Deposit( double dAmount, char *szPassword )  
{  
   if ( Validate( szPassword ) )  
      return Deposit( dAmount );  
   else  
      return 0.0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen (C++)](../cpp/functions-cpp.md)
