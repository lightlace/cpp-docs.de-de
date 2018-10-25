---
title: Postfixausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], postfix
- postfix expressions
- expressions [C++], postfix
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d28d909866808fbffb6165e552bf825bf1241771
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069814"
---
# <a name="postfix-expressions"></a>Postfixausdrücke

Postfixausdrücke bestehen aus primären Ausdrücken bzw. Ausdrücken, in denen Postfixoperatoren einem primären Ausdruck folgen. Die Postfix-Operatoren sind in der folgenden Tabelle aufgeführt.

### <a name="postfix-operators"></a>Postfix-Operatoren

|Name des Operators|Operator-Notation|
|-------------------|-----------------------|
|[Subscript-operator](../cpp/subscript-operator.md)|**[ ]**|
|[Funktionsaufrufoperator](../cpp/function-call-operator-parens.md)|**( )**|
|[Operator für die explizite Konvertierung](../cpp/explicit-type-conversion-operator-parens.md)|*Typname* **)**|
|[Memberzugriffsoperator](../cpp/member-access-operators-dot-and.md)|**.** Oder **->**|
|[Postfixinkrement-Operators](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**++**|
|[Postfixdekrement-Operators](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**--**|

Die folgende Syntax beschreibt mögliche Postfixausdrücke:

```
primary-expression 
postfix-expression[expression]postfix-expression(expression-list)simple-type-name(expression-list)postfix-expression.namepostfix-expression->namepostfix-expression++postfix-expression--cast-keyword < typename > (expression )typeid ( typename )
```

Die *Postfix-Expression* über ein primärer Ausdruck oder ein anderer postfixausdruck sein.  Finden Sie unter **primärausdrücke**.  Postfixausdrücke gruppieren sich von links nach rechts und ermöglichen so das Verketten der Ausdrücke wie folgt:

```cpp
func(1)->GetValue()++
```

Im obigen Ausdruck `func` ist ein primärer Ausdruck, `func(1)` ist eine Funktions-postfixausdruck, `func(1)->GetValue` ist ein postfixausdruck, der einen Member der Klasse `func(1)->GetValue()` ist eine andere Funktions-postfixausdruck, und die gesamte Ausdruck ist ein postfixausdruck, den Rückgabewert von "GetValue".  Die Bedeutung des Ausdrucks als Ganzes ist „Funktion aufrufen, dabei 1 als Argument übergeben und einen Zeiger für eine Klasse als Rückgabewert erhalten.  Rufen Sie anschließend `GetValue()` für diese Klasse, klicken Sie dann den zurückgegebenen Wert erhöhen.

Die oben aufgeführten Ausdrücke sind Zuweisungsausdrücke, was bedeutet, dass das Ergebnis dieser Ausdrücke ein "r-value" sein muss.

Die Form des Postfixausdrucks

```cpp
simple-type-name ( expression-list )
```

gibt den Aufruf des Konstruktors an.  Wenn "simple-type-name" ein grundlegender Typ ist, muss die Ausdrucksliste ein einzelner Ausdruck sein, und dieser Ausdruck gibt eine Umwandlung des Werts des Ausdrucks in den einfachen Typ an.  Dieser Typ von Umwandlungsausdruck imitiert einen Konstruktor.  Da diese Form die Konstruktion grundlegender Klassen und Typen mit derselben Syntax ermöglicht, ist sie bei der Definition von Vorlagenklassen besonders nützlich.

Die *Cast-Keyword* ist einer der **Dynamic_cast**, **"static_cast"** oder **"reinterpret_cast"**.  Weitere Informationen finden Sie unter **Dynamic_cast**, **"static_cast"** und **Reinterpet_cast**.

Die **Typeid** -Operator gilt ein postfixausdruck.  Finden Sie unter **Typeid-Operator**.

## <a name="formal-and-actual-arguments"></a>Formale und tatsächliche Argumente

Aufrufende Programme übergeben Informationen an die aufgerufenen Funktionen in "tatsächlichen Argumenten". Die aufgerufenen Funktionen greifen mithilfe der entsprechenden "formalen Argumente" auf die Informationen zu.

Wenn eine Funktion aufgerufen wird, werden die folgenden Aufgaben ausgeführt:

- Alle tatsächlichen Argumente (die vom Aufrufer angegebenen) werden ausgewertet. Es gibt keine implizite Reihenfolge, in der diese Argumente ausgewertet werden. Alle Argumente werden jedoch ausgewertet, und alle Nebeneffekte werden vor dem Eintritt in die Funktion abgeschlossen.

- Jedes formale Argument wird mit dem entsprechenden tatsächlichen Argument in der Ausdrucksliste initialisiert. (Ein formales Argument ist ein Argument, das im Funktionsheader deklariert und im Text einer Funktion verwendet wird.) Konvertierungen werden wie durch Initialisierung ausgeführt. Sowohl Standard- als auch benutzerdefinierte Konvertierungen werden beim Konvertieren eines tatsächlichen Arguments in den richtigen Typ ausgeführt. Die ausgeführte Initialisierung wird durch den folgenden Code konzeptionell veranschaulicht:

    ```cpp
    void Func( int i ); // Function prototype
    ...
    Func( 7 );          // Execute function call
    ```

   Die konzeptionellen Initialisierungen vor dem Aufruf sind:

    ```cpp
    int Temp_i = 7;
    Func( Temp_i );
    ```

   Beachten Sie, dass die Initialisierung ausgeführt wird, als würde die Gleichheitszeichensyntax anstelle der Klammersyntax verwendet werden. Eine Kopie von `i` wird vor dem Übergeben des Werts an die Funktion erstellt. (Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md) und [Konvertierungen](../cpp/user-defined-type-conversions-cpp.md)).

   Aus diesem Grund der Funktionsprototyp (Deklaration) für ein Argument des Typs aufgerufen **lange**, und wenn das aufrufende Programm ein tatsächliches Argument des Typs bereitstellt **Int**, das tatsächliche Argument höher gestuft wird mit einer standardkonvertierung in den Typ **lange** (finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md)).

   Es ist ein Fehler, ein tatsächliches Argument anzugeben, für das es keine Standard- oder benutzerdefinierte Konvertierung in den Typ des formalen Arguments gibt.

   Für die tatsächlichen Argumente des Klassentyps wird das formale Argument initialisiert, indem der Konstruktor der Klasse aufgerufen wird. (Finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md) für Weitere Informationen zu diesen speziellen Klassenmemberfunktionen.)

- Der Funktionsaufruf wird ausgeführt.

Das folgende Programmfragment zeigt einen Funktionsaufruf:

```cpp
// expre_Formal_and_Actual_Arguments.cpp
void func( long param1, double param2 );

int main()
{
    long i = 1;
    double j = 2;

    // Call func with actual arguments i and j.
    func( i, j );
}

// Define func with formal parameters param1 and param2.
void func( long param1, double param2 )
{
}
```

Wenn `func` Main, den formalen Parameter aufgerufen wird `param1` wird initialisiert, durch den Wert der `i` (`i` ist in den Typ konvertiert **lange** in den richtigen Typ mithilfe eines Standarddialogfelds entsprechen -Konvertierung), und der formale Parameter `param2` wird initialisiert, durch den Wert der `j` (`j` ist in den Typ konvertiert **doppelte** mithilfe einer standardkonvertierung).

## <a name="treatment-of-argument-types"></a>Behandlung von Argumenttypen

Formale Argumente, die als const-Typen deklariert sind, können im Funktionstext nicht geändert werden. Funktionen können ein der Argumente, die nicht vom Typ ändern **const**. Die Änderung ist jedoch auf die Funktion beschränkt und wirkt sich nicht der tatsächliche Wert des Arguments, wenn das tatsächliche Argument um einen Verweis auf ein Objekt nicht vom Typ wurde **const**.

Die folgenden Funktionen veranschaulichen einige dieser Konzepte:

```cpp
// expre_Treatment_of_Argument_Types.cpp
int func1( const int i, int j, char *c ) {
   i = 7;   // C3892 i is const.
   j = i;   // value of j is lost at return
   *c = 'a' + j;   // changes value of c in calling function
   return i;
}

double& func2( double& d, const char *c ) {
   d = 14.387;   // changes value of d in calling function.
   *c = 'a';   // C3892 c is a pointer to a const object.
    return d;
}
```

## <a name="ellipses-and-default-arguments"></a>Ellipsen und Standardargumente

Funktionen können deklariert werden, um weniger Argumente als in der Funktionsdefinition angegeben mit einer der folgenden beiden Methoden zu akzeptieren: Auslassungspunkte (`...`) oder Standardargumente.

Auslassungspunkte geben an, dass Argumente möglicherweise erforderlich sind, dass die Anzahl und Typen jedoch nicht in der Deklaration angegeben werden. Dies ist normalerweise ein schlechtes Beispiel für C++-Programmierung, da es einen der Vorteile von C++ unterlaufen kann: Typsicherheit. Verschiedene Konvertierungen werden auf Funktionen angewendet, die mit Auslassungszeichen deklariert sind, und nicht auf jene Funktionen, deren formale und tatsächliche Argumenttypen bekannt sind:

- Wenn das tatsächliche Argument vom Typ **"float"**, er wird höher gestuft, Typ **doppelte** vor dem Funktionsaufruf.

- Alle mit oder ohne Vorzeichen **Char**, **kurze**, enumerierte Typ bzw. Bitfeld ist entweder eine signierte oder eine unsignierte konvertiert **Int** mittels ganzzahliger heraufstufung.

- Jedes Argument des Klassentyps wird durch einen Wert als Datenstruktur übergeben; die Kopie wird durch Kopieren der Binärdatei statt durch Aufrufen des Kopierkonstruktors der Klasse erstellt (falls vorhanden).

Ellipsen müssen in der Argumentliste zuletzt deklariert werden, sofern sie vorhanden sind. Weitere Informationen zum Übergeben einer Variablen Anzahl von Argumenten finden Sie unter der Erläuterung [Va_arg, Va_start und Va_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) in die *Run-Time Library Reference*.

Weitere Informationen zu Standardargumenten in CLR-Programmierung finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).

Mit Standardargumenten können Sie den Wert festlegen, den ein Argument annehmen soll, wenn keiner im Funktionsaufruf angegeben wird. Das folgende Codefragment zeigt, wie Standardargumente funktionieren. Weitere Informationen zu Einschränkungen für das Festlegen von Standardargumenten, finden Sie unter [Standardargumente](../cpp/default-arguments.md).

```cpp
// expre_Ellipses_and_Default_Arguments.cpp
// compile with: /EHsc
#include <iostream>

// Declare the function print that prints a string,
// then a terminator.
void print( const char *string,
            const char *terminator = "\n" );

int main()
{
    print( "hello," );
    print( "world!" );

    print( "good morning", ", " );
    print( "sunshine." );
}

using namespace std;
// Define print.
void print( const char *string, const char *terminator )
{
    if( string != NULL )
        cout << string;

    if( terminator != NULL )
        cout << terminator;
}
```

Das vorangehende Programm deklariert eine Funktion, `print`, die zwei Argumente akzeptiert. Allerdings das zweite Argument, *Abschlusszeichen*, hat den Standardwert `"\n"`. In `main`, die ersten beiden Aufrufe von `print` ermöglichen das zweite Standardargument, geben Sie eine neue Zeile ein, um die gedruckte Zeichenfolge zu beenden. Der dritte Aufruf gibt einen expliziten Wert für das zweite Argument zurück. Die Ausgabe des Programms lautet

```Output
hello,
world!
good morning, sunshine.
```

## <a name="see-also"></a>Siehe auch

[Ausdruckstypen](../cpp/types-of-expressions.md)