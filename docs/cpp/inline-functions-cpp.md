---
title: Inlinefunktionen [C++]
ms.date: 10/09/2018
f1_keywords:
- __forceinline_cpp
- __inline_cpp
- inline_cpp
- __inline
- _inline
- __forceinline
- _forceinline
helpviewer_keywords:
- inline functions [C++], class members
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
ms.openlocfilehash: 55cf598877c2447e0f80e783b53b290699042b8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607817"
---
# <a name="inline-functions-c"></a>Inlinefunktionen [C++]

Eine Funktion, die im Text einer Klassendeklaration definiert ist, ist eine Inlinefunktion.

## <a name="example"></a>Beispiel

In der folgenden Klassendeklaration ist der `Account`-Konstruktor eine Inlinefunktion. Die Memberfunktionen `GetBalance`, `Deposit`, und `Withdraw` nicht als angegeben sind **Inline** aber als Inlinefunktion implementiert werden können.

```cpp
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
>  Die Deklaration der Klasse, die Funktionen deklariert wurden, ohne die **Inline** Schlüsselwort. Die **Inline** Schlüsselwort kann in der Klassendeklaration angegeben werden; das Ergebnis ist identisch.

Eine angegebene Inlinememberfunktion muss in jeder Kompilierungseinheit auf die gleiche Weise deklariert werden. Diese Einschränkung bewirkt, dass sich Inlinefunktionen wie instanziierte Funktionen verhalten. Außerdem muss es genau eine Definition einer Inlinefunktion geben.

Eine Klassenmemberfunktion standardmäßig zu externer Bindung, es sei denn, eine Definition für diese Funktion enthält die **Inline** Spezifizierer. Das vorhergehende Beispiel zeigt, dass diese Funktionen nicht explizit mit deklariert werden, müssen die **Inline** Spezifizierer, mit **Inline** in der Funktion Definition bewirkt, dass es eine Inlinefunktion handelt. Es ist jedoch nicht zulässig, eine Funktion als erneut **Inline** nach einem Aufruf der Funktion.

## <a name="inline-inline-and-forceinline"></a>Inline __inline, und \__forceinline

Die **Inline** und **"__inline"** Spezifizierer den Compiler anweisen, eine Kopie des Funktionstexts an jeder Stelle einzufügen, die Funktion wird aufgerufen.

Die Einfügung (bezeichnet als Inlineerweiterung oder Inlinekonstrukt) wird nur ausgeführt, wenn die Kosten-Nutzen-Analyse des Compilers dies als sinnvoll bewertet. Eine Inlineerweiterung verringert den Funktionsaufruf-Mehraufwand, möglicherweise auf Kosten der größeren Codegröße.

Die **"__forceinline"** Schlüsselwort überschreibt die Kosten-Nutzen-Analyse und basiert auf dem Urteil des Programmierers stattdessen. Vorsicht verwenden **"__forceinline"**. Wahllose Verwendung von **"__forceinline"** größere Code mit nur marginalen Leistungssteigerungen oder führen, in einigen Fällen sogar Leistungsverlusten (aufgrund des erweiterten Pagings einer größeren ausführbaren Datei, z. B.).

Die Verwendung von Inlinefunktionen kann das Programm schneller machen, da so der Mehraufwand vermieden wird, der Funktionsaufrufen zugeordnet ist. Inline erweiterte Funktionen unterliegen Codeoptimierungen, die für normale Funktionen nicht verfügbar sind.

Der Compiler behandelt die Inlineerweiterungsoptionen und -Schlüsselwörter als Vorschläge. Es gibt keine Garantie, dass Funktionen inline gestellt werden. Sie können den Compiler auf eine bestimmte Funktion, nicht zwingen, trotz der **"__forceinline"** Schlüsselwort. Beim Kompilieren mit **"/ CLR"**, der Compiler wird nicht Inline eine Funktion, wenn Sicherheitsattribute auf die Funktion angewendet.

Die **Inline** Schlüsselwort ist nur in C++ verfügbar. Die **"__inline"** und **"__forceinline"** Schlüsselwörter sind in C und C++ verfügbar. Für die Kompatibilität mit früheren Versionen **_inline** und **_forceinline** sind Synonyme für **"__inline"**, und **"__forceinline"** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

Die **Inline** -Schlüsselwort weist den Compiler an, dass die Inlineerweiterung bevorzugt wird. Jedoch kann der Compiler eine separate Instanz der Funktion erstellen (instanziieren) und Standardaufrufbindungen erstellen, anstatt den Code inline einzufügen. Zwei Fälle, in denen dies auftreten kann, sind:

- Rekursive Funktionen.

- Funktionen, auf die durch einen Zeiger an anderer Stelle in der Übersetzungseinheit verwiesen wird.

Diese Gründe beeinträchtigen möglicherweise Inlining, dem Kompromiss *als andere Mai*, nach dem Ermessen des Compilers, Sie sollten nicht abhängig der **Inline** Bezeichner eine Funktion inline zu verursachen.

Wie bei normalen Funktionen so ist auch bei den Argumenten einer Inlinefunktion die Reihenfolge der Auswertung nicht festgelegt. Tatsächlich kann sie sich von der Reihenfolge unterscheiden, in der die Argumente ausgewertet werden, wenn sie mithilfe des normalen Funktionsaufrufprotokolls übergeben werden.

Die [tatsächlich](../build/reference/ob-inline-function-expansion.md) kann bestimmen, ob die Inlinefunktionserweiterung tatsächlich auftritt.

[/ LTCG](../build/reference/ltcg-link-time-code-generation.md) führt modulübergreifende inlinekonstrukte, unabhängig davon, ob er im Quellcode angefordert wurde.

### <a name="example-1"></a>Beispiel 1

```cpp
// inline_keyword1.cpp
// compile with: /c
inline int max( int a , int b ) {
   if( a > b )
      return a;
   return b;
}
```

Memberfunktionen einer Klasse können entweder mit Inline deklariert werden die **Inline** Schlüsselwort oder indem Sie die Funktionsdefinition innerhalb der Klassendefinition platzieren.

### <a name="example-2"></a>Beispiel 2

```cpp
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

Die **"__inline"** -Schlüsselwort ist äquivalent zu **Inline**.

Selbst bei **"__forceinline"**, der Compiler kann nicht Inline-Code in allen Fällen. Der Compiler kann keine Funktion inline setzen, wenn Folgendes der Fall ist:

- Die Funktion oder ihr Aufrufer werden mit /Ob0 kompiliert (die Standardoption für Debugbuilds).

- Die Funktion und der Aufrufer verwenden unterschiedliche Typen der Ausnahmebehandlung (C++-Ausnahmebehandlung zum einen, strukturierte Ausnahmebehandlung zum anderen).

- Die Funktion weist eine variable Argumentliste auf.

- Die Funktion verwendet eine Inlineassembly, es sei denn, sie wird mit /Og, /Ox, /O1, oder /O2 kompiliert.

- Die Funktion ist rekursiv und nicht zusammen mit **#pragma inline_recursion(on)**. Mit dem Pragma werden rekursive Funktionen mit einer Standardtiefe von 16 Aufrufen inline gesetzt. Um die Tiefe bei inlinekonstrukten zu reduzieren, verwenden Sie [Inline_depth](../preprocessor/inline-depth.md) Pragma.

- Die Funktion ist virtuell und wird virtuell aufgerufen. Direkte Aufrufe virtueller Funktionen können inline gesetzt werden.

- Das Programm akzeptiert die Adresse der Funktion, und der Aufruf erfolgt über den Zeiger auf die Funktion. Direkte Aufrufe von Funktionen, deren Adresse akzeptiert wurden, können inline gesetzt werden.

- Die Funktion ist auch mit markiert die [naked](../cpp/naked-cpp.md) [__declspec](../cpp/declspec.md) Modifizierer.

Wenn der Compiler nicht Inline stellen kann eine Funktion deklariert, mit **"__forceinline"**, es wird eine Warnung der Stufe 1, außer wenn generiert:

- Die Funktion wird mit/od "oder" / Ob0 kompiliert. Keine inlineersetzung in diesen Fällen wird erwartet.

- Die Funktion wird in einer Bibliothek oder einer anderen Übersetzungseinheit, extern definiert oder wird ein virtueller Aufruf oder ein Ziel von indirekten Aufruf. Der Compiler kann nicht auf nicht-inline-Code identifiziert, die nicht in der aktuellen Übersetzungseinheit.

Rekursive Funktionen können Inline ersetzt, um eine gemäß Tiefe werden die [Inline_depth](../preprocessor/inline-depth.md) Pragma bis maximal 16 aufrufen. Nach dieser Tiefe werden rekursive Funktionsaufrufe als Aufrufe einer Instanz der Funktion behandelt.  Die Tiefe, bis zu der rekursive Funktionen durch die Inlineheuristik geprüft werden, kann 16 nicht überschreiten. Die [Inline_recursion](../preprocessor/inline-recursion.md) Pragma steuert die Inlineerweiterung einer Funktion derzeit unter der Erweiterung. Finden Sie unter den [Inlinefunktionserweiterung](../build/reference/ob-inline-function-expansion.md) (/ Ob)-Compileroption Weitere Informationen.

**Ende Microsoft-spezifisch**

Weitere Informationen zur Verwendung der **Inline** Spezifizierer, finden Sie unter:

- [Inline-Klassenmemberfunktionen](../cpp/inline-functions-cpp.md)

- [Definieren von C++-Inlinefunktionen mit dllexport und dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

## <a name="when-to-use-inline-functions"></a>Verwendungsmöglichkeiten von Inlinefunktionen

Inlinefunktionen werden am besten für kleine Funktionen verwendet, z. B. Zugriff auf private Datenmember. Ein- oder zweispurige "Accessor"-Funktionen geben in erster Linie Zustandsinformationen über Objekte ab. Kurze Funktionen werden von der Restkapazität des Funktionsaufrufs beeinflusst. Längere Funktionen benötigen proportional weniger Zeit in der Aufruf-/Rückgabesequenz und profitieren weniger vom Inlining.

Ein `Point` Klasse kann wie folgt definiert werden:

```cpp
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

Koordinatenmanipulation ist ein relativ allgemeiner Vorgang in einem Client, der dieser Klasse und durch Angabe der beiden zugriffsmethodenfunktionen (`x` und `y` im vorherigen Beispiel) als **Inline** speichert Sie in der Regel die der Mehraufwand für:

- Funktionsaufrufen (einschließlich der Parameterübergabe und -ablage der Adresse des Objekts auf dem Stapel)

- Beibehaltung des Stapelrahmens des Aufrufers

- Neuem Stapelrahmensetup

- Rückgabewertkommunikation

- Wiederherstellung des alten Stapelrahmens

- Zurück

## <a name="inline-functions-vs-macros"></a>Inlinefunktionen im Vergleich zu Makros

Obwohl Inlinefunktionen Makros ähneln (da der Funktionscode zum Zeitpunkt des Aufrufs zur Kompilierzeit erweitert wird), werden Inlinefunktionen vom Compiler analysiert, während Makros vom Präprozessor erweitert werden. Folglich gibt es einige wichtige Unterschiede:

- Inlinefunktionen folgen allen Protokollen des Typs mit erzwungener Sicherheit auf normalen Funktionen.

- Inlinefunktionen werden angegeben, mit derselben Syntax wie jede andere Funktion, mit dem Unterschied, dass sie enthalten die **Inline** Schlüsselwort in der Funktionsdeklaration.

- Die Ausdrücke, die als Argumente an Inlinefunktionen übergeben werden, werden einmal ausgewertet. In einigen Fällen können die Ausdrücke, die als Argumente an Makros übergeben werden, mehrmals ausgewertet werden.

Das folgende Beispiel zeigt ein Makro, das Kleinbuchstaben in Großbuchstaben konvertiert:

```cpp
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

Der Zweck des Ausdrucks `toupper(getc(stdin))` besteht darin, dass ein Zeichen aus der Konsole gelesen werden soll (`stdin`) und bei Bedarf in Großbuchstaben konvertiert wurden.

Aufgrund der Implementierung des Makros wird `getc` einmal ausgeführt, um zu bestimmen, ob das Zeichen größer oder gleich "a" ist, und einmal, um zu bestimmen, ob es ist kleiner oder gleich "z" ist. Wenn es sich in diesem Bereich befindet, wird `getc` erneut ausgeführt, um das Zeichen in einen Großbuchstaben zu konvertieren. Dies bedeutet, dass das Programm auf zwei oder drei Zeichen wartet, obwohl es idealerweise nur auf eines warten sollte.

Inlinefunktionen beheben das zuvor beschriebene Problem:

```cpp
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

[noinline](../cpp/noinline.md)<br/>
[auto_inline](../preprocessor/auto-inline.md)