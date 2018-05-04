---
title: Inlinefunktionen (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6661996669e454e655d0149f1dbb1df505116469
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="inline-functions-c"></a>Inlinefunktionen [C++]
Eine Funktion, die im Text einer Klassendeklaration definiert ist, ist eine Inlinefunktion.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Klassendeklaration ist der `Account`-Konstruktor eine Inlinefunktion. Die Memberfunktionen `GetBalance`, `Deposit`, und `Withdraw` nicht als angegeben sind **Inline** aber als Inlinefunktion implementiert werden können.  
  
```  
// Inline_Member_Functions.cpp  
class Account  
{  
public:  
    Account(double initial_balance) { balance = initial_balance; }  
    double GetBalance();  
    double Deposit( double Amount );  
    double Withdraw( double Amount );  
private:  
    double balance;  
};  
  
inline double Account::GetBalance()  
{  
    return balance;  
}  
  
inline double Account::Deposit( double Amount )  
{  
    return ( balance += Amount );  
}  
  
inline double Account::Withdraw( double Amount )  
{  
    return ( balance -= Amount );  
}  
int main()  
{  
}  
```  
  
> [!NOTE]
>  In der Klassendeklaration wurden die Funktionen deklariert, ohne die **Inline** Schlüsselwort. Die **Inline** Schlüsselwort kann in der Klassendeklaration angegeben werden; das Ergebnis identisch.  
  
 Eine angegebene Inlinememberfunktion muss in jeder Kompilierungseinheit auf die gleiche Weise deklariert werden. Diese Einschränkung bewirkt, dass sich Inlinefunktionen wie instanziierte Funktionen verhalten. Außerdem muss es genau eine Definition einer Inlinefunktion geben.  
  
 Eine Klassenmemberfunktion standardmäßig zu externer Bindung, es sei denn, eine Definition für diese Funktion enthält die **Inline** Spezifizierer. Das vorhergehende Beispiel zeigt, dass diese Funktionen nicht explizit mit deklariert werden, müssen die **Inline** Spezifizierer; mit **Inline** in der Funktion Definition bewirkt, dass es eine Inlinefunktion handelt. Allerdings ist es nicht zulässig, deklarieren Sie eine Funktion als **Inline** nach einem Aufruf der Funktion.  
  
## <a name="inline-inline-and-forceinline"></a>Inline __inline, und \__forceinline  
 Die Spezifizierer `inline` und `__inline` weisen den Compiler an, eine Kopie des Funktionstexts an jeder Stelle einzufügen, an der die Funktion aufgerufen wird.  
  
 Die Einfügung (bezeichnet als Inlineerweiterung oder Inlinekonstrukt) wird nur ausgeführt, wenn die Kosten-Nutzen-Analyse des Compilers dies als sinnvoll bewertet. Eine Inlineerweiterung verringert den Funktionsaufruf-Mehraufwand, möglicherweise auf Kosten der größeren Codegröße.  
  
 Das `__forceinline`-Schlüsselwort überschreibt die Kosten-Nutzen-Analyse und basiert stattdessen auf dem Urteil des Programmierers. Sie sollten `__forceinline` mit Vorsicht verwenden. Die wahllose Verwendung von `__forceinline` kann zu längerem Code mit nur marginalen Leistungssteigerungen oder in einigen Fällen sogar mit Leistungsverlusten führen (beispielsweise aufgrund des erweiterten Pagings einer größeren ausführbaren Datei).  
  
 Die Verwendung von Inlinefunktionen kann das Programm schneller machen, da so der Mehraufwand vermieden wird, der Funktionsaufrufen zugeordnet ist. Inline erweiterte Funktionen unterliegen Codeoptimierungen, die für normale Funktionen nicht verfügbar sind.  
  
 Der Compiler behandelt die Inlineerweiterungsoptionen und -Schlüsselwörter als Vorschläge. Es gibt keine Garantie, dass Funktionen inline gestellt werden. Sie können den Compiler nicht zwingen, eine bestimmte Funktion inline zu setzen, auch nicht mit dem `__forceinline`-Schlüsselwort. Beim Kompilieren mit **"/ CLR"**, der Compiler wird nicht Inline eine Funktion, wenn Sicherheitsattribute auf die Funktion angewendet.  
  
 Die **Inline** -Schlüsselwort ist nur in C++ verfügbar. Die Schlüsselwörter `__inline` und `__forceinline` sind sowohl in C als auch in C++ verfügbar. Um die Kompatibilität mit früheren Versionen **_inline** ist ein Synonym für `__inline`.  
  
 Die **Inline** -Schlüsselwort weist den Compiler an, dass Inlineerweiterung bevorzugt wird. Jedoch kann der Compiler eine separate Instanz der Funktion erstellen (instanziieren) und Standardaufrufbindungen erstellen, anstatt den Code inline einzufügen. Zwei Fälle, in denen dies auftreten kann, sind:  
  
-   Rekursive Funktionen.  
  
-   Funktionen, auf die durch einen Zeiger an anderer Stelle in der Übersetzungseinheit verwiesen wird.  
  
 Diese Gründe beeinträchtigen möglicherweise inlinekonstrukte, *wie andere*, nach dem Ermessen des Compilers; Sie sollten nicht richten sich nach der **Inline** Spezifizierer, um eine Funktion inline zu setzen.  
  
 Wie bei normalen Funktionen so ist auch bei den Argumenten einer Inlinefunktion die Reihenfolge der Auswertung nicht festgelegt. Tatsächlich kann sie sich von der Reihenfolge unterscheiden, in der die Argumente ausgewertet werden, wenn sie mithilfe des normalen Funktionsaufrufprotokolls übergeben werden.  
  
 Die [tatsächlich](../build/reference/ob-inline-function-expansion.md) Optimierung (Compileroption) hilft um zu bestimmen, ob die Inlinefunktionserweiterung tatsächlich eintritt.  
  
 [/ LTCG](../build/reference/ltcg-link-time-code-generation.md) führt modulübergreifende inlinekonstrukte aus, unabhängig davon, ob dies im Quellcode angefordert wurde.  
  
### <a name="example-1"></a>Beispiel 1  
  
```  
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 Memberfunktionen einer Klasse können entweder mit Inline deklariert werden die **Inline** Schlüsselwort oder die Funktionsdefinition innerhalb der Klassendefinition platziert.  
  
### <a name="example-2"></a>Beispiel 2  
  
```  
// inline_keyword2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
  
class MyClass {  
public:  
   void print() { cout << i << ' '; }   // Implicitly inline  
private:  
   int i;  
};  
```  
  
### <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die `__inline` -Schlüsselwort ist äquivalent zu **Inline**.  
  
 Auch mit `__forceinline` kann der Compiler Code nicht in allen Fällen inline setzen. Der Compiler kann keine Funktion inline setzen, wenn Folgendes der Fall ist:  
  
-   Die Funktion oder ihr Aufrufer werden mit /Ob0 kompiliert (die Standardoption für Debugbuilds).  
  
-   Die Funktion und der Aufrufer verwenden unterschiedliche Typen der Ausnahmebehandlung (C++-Ausnahmebehandlung zum einen, strukturierte Ausnahmebehandlung zum anderen).  
  
-   Die Funktion weist eine variable Argumentliste auf.  
  
-   Die Funktion verwendet eine Inlineassembly, es sei denn, sie wird mit /Og, /Ox, /O1, oder /O2 kompiliert.  
  
-   Die Funktion ist rekursiv und nicht beiliegen **#pragma inline_recursion(on)**. Mit dem Pragma werden rekursive Funktionen mit einer Standardtiefe von 16 Aufrufen inline gesetzt. Um die Tiefe bei inlinekonstrukten zu reduzieren, verwenden Sie [Inline_depth](../preprocessor/inline-depth.md) Pragma.  
  
-   Die Funktion ist virtuell und wird virtuell aufgerufen. Direkte Aufrufe virtueller Funktionen können inline gesetzt werden.  
  
-   Das Programm akzeptiert die Adresse der Funktion, und der Aufruf erfolgt über den Zeiger auf die Funktion. Direkte Aufrufe von Funktionen, deren Adresse akzeptiert wurden, können inline gesetzt werden.  
  
-   Die Funktion wird ebenfalls mit markiert die [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) Modifizierer.  
  
 Wenn der Compiler Inline nicht deklariert eine Funktion mit `__forceinline`, es wird eine Warnung der Stufe 1, außer wenn generiert:
  
-   Die Funktion wird mithilfe von/od oder/Ob0 kompiliert. Keine inlining in diesen Fällen wird erwartet.     
  
-   Die Funktion ist extern in einer Bibliothek oder einer anderen Übersetzungseinheit definiert oder eine virtuelle Aufrufziel oder indirekte Aufrufziel. Der Compiler kann nicht mit nicht-Inlining Code identifiziert, die nicht in der aktuellen Übersetzungseinheit.  
  
 Rekursive Funktionen können Inline ersetzt in einer Tiefe von angegeben werden die [Inline_depth](../preprocessor/inline-depth.md) Pragma, bis zu maximal 16 aufrufen. Nach dieser Tiefe werden rekursive Funktionsaufrufe als Aufrufe einer Instanz der Funktion behandelt.  Die Tiefe, bis zu der rekursive Funktionen durch die Inlineheuristik geprüft werden, kann 16 nicht überschreiten. Die [Inline_recursion](../preprocessor/inline-recursion.md) Pragma steuert die Inlineerweiterung einer Funktion derzeit in der Erweiterung. Finden Sie unter der [Inlinefunktionserweiterung](../build/reference/ob-inline-function-expansion.md) (/ Ob)-Compileroption nach diesbezüglichen Informationen.  
  
**Ende Microsoft-spezifisch**  
 Weitere Informationen zur Verwendung der **Inline** Spezifizierer, finden Sie unter:  
  
-   [Inline-Klassenmemberfunktionen](../cpp/inline-functions-cpp.md)  
  
-   [Definieren von C++-Inlinefunktionen mit dllexport und dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## <a name="when-to-use-inline-functions"></a>Verwendungsmöglichkeiten von Inlinefunktionen  
 Inlinefunktionen werden am besten für kleine Funktionen verwendet, z. B. Zugriff auf private Datenmember. Ein- oder zweispurige "Accessor"-Funktionen geben in erster Linie Zustandsinformationen über Objekte ab. Kurze Funktionen werden von der Restkapazität des Funktionsaufrufs beeinflusst. Längere Funktionen benötigen proportional weniger Zeit in der Aufruf-/Rückgabesequenz und profitieren weniger vom Inlining.  
  
 Ein `Point` Klasse wie folgt definiert werden:  
  
```  
// when_to_use_inline_functions.cpp  
class Point  
{  
public:  
    // Define "accessor" functions as  
    //  reference types.  
    unsigned& x();  
    unsigned& y();  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
inline unsigned& Point::x()  
{  
    return _x;  
}  
inline unsigned& Point::y()  
{  
    return _y;  
}  
int main()  
{  
}  
```  
  
 Koordinatenmanipulation ist ein relativ allgemeiner Vorgang in einem Client dieser Klasse, die Angabe der beiden Accessorfunktionen (`x` und `y` im vorherigen Beispiel) als **Inline** speichert Sie in der Regel die der Mehraufwand für:  
  
-   Funktionsaufrufen (einschließlich der Parameterübergabe und -ablage der Adresse des Objekts auf dem Stapel)  
  
-   Beibehaltung des Stapelrahmens des Aufrufers  
  
-   Neuem Stapelrahmensetup  
  
-   Rückgabewertkommunikation  
  
-   Wiederherstellung des alten Stapelrahmens  
  
-   Zurück  
  
## <a name="inline-functions-vs-macros"></a>Inlinefunktionen im Vergleich zu Makros  
 Obwohl Inlinefunktionen Makros ähneln (da der Funktionscode zum Zeitpunkt des Aufrufs zur Kompilierzeit erweitert wird), werden Inlinefunktionen vom Compiler analysiert, während Makros vom Präprozessor erweitert werden. Folglich gibt es einige wichtige Unterschiede:  
  
-   Inlinefunktionen folgen allen Protokollen des Typs mit erzwungener Sicherheit auf normalen Funktionen.  
  
-   Inlinefunktionen werden angegeben, die mit derselben Syntax wie jede andere Funktion, mit dem Unterschied, dass sie enthalten die **Inline** Schlüsselwort in der Funktionsdeklaration.  
  
-   Die Ausdrücke, die als Argumente an Inlinefunktionen übergeben werden, werden einmal ausgewertet. In einigen Fällen können die Ausdrücke, die als Argumente an Makros übergeben werden, mehrmals ausgewertet werden.  
  
 Das folgende Beispiel zeigt ein Makro, das Kleinbuchstaben in Großbuchstaben konvertiert:  
  
```  
// inline_functions_macro.c  
#include <stdio.h>  
#include <conio.h>  
  
#define toupper(a) ((a) >= 'a' && ((a) <= 'z') ? ((a)-('a'-'A')):(a))  
  
int main() {  
   char ch;  
   printf_s("Enter a character: ");  
   ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
//  Sample Input:  xyz  
// Sample Output:  Z  
  
```  
  
 Der Zweck des Ausdrucks `toupper(getc(stdin))` ist, dass ein Zeichen aus der Konsole gelesen werden soll (`stdin`) und bei Bedarf in Großbuchstaben konvertiert wurden.  
  
 Aufgrund der Implementierung des Makros wird `getc` einmal ausgeführt, um zu bestimmen, ob das Zeichen größer oder gleich "a" ist, und einmal, um zu bestimmen, ob es ist kleiner oder gleich "z" ist. Wenn es sich in diesem Bereich befindet, wird `getc` erneut ausgeführt, um das Zeichen in einen Großbuchstaben zu konvertieren. Dies bedeutet, dass das Programm auf zwei oder drei Zeichen wartet, obwohl es idealerweise nur auf eines warten sollte.  
  
 Inlinefunktionen beheben das zuvor beschriebene Problem:  
  
```  
// inline_functions_inline.cpp  
#include <stdio.h>  
#include <conio.h>  
  
inline char toupper( char a ) {  
   return ((a >= 'a' && a <= 'z') ? a-('a'-'A') : a );  
}  
  
int main() {  
   printf_s("Enter a character: ");  
   char ch = toupper( getc(stdin) );  
   printf_s( "%c", ch );  
}  
```  
  
```Output  
Sample Input: a  
Sample Output: A  
```  
  
## <a name="see-also"></a>Siehe auch  
 [noinline](../cpp/noinline.md)   
 [auto_inline](../preprocessor/auto-inline.md)