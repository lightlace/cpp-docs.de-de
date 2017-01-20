---
title: "Postfixausdr&#252;cke"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausdrücke [C++], Postfix"
  - "Operatoren [C++], Postfix"
  - "Postfixausdrücke"
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Postfixausdr&#252;cke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Postfixausdrücke bestehen aus primären Ausdrücken bzw. Ausdrücken, in denen Postfixoperatoren einem primären Ausdruck folgen.  Die Postfix\-Operatoren sind in der folgenden Tabelle aufgeführt.  
  
### Postfix\-Operatoren  
  
|Name des Operators|Operator\-Notation|  
|------------------------|------------------------|  
|[Indexoperator](../cpp/subscript-operator.md)|**\[ \]**|  
|[Funktionsaufrufoperator](../cpp/function-call-operator-parens.md)|**\( \)**|  
|[Operator für die explizite Typkonvertierung](../cpp/explicit-type-conversion-operator-parens.md)|*type\-name* **\( \)**|  
|[Memberzugriffsoperator](../cpp/member-access-operators-dot-and.md)|**.** oder **–\>**|  
|[Postfix\-Operator für Inkrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Postfix\-Operator für Dekrement](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**––**|  
  
 Die folgende Syntax beschreibt mögliche Postfixausdrücke:  
  
```  
  
          primary-expression   
postfix-expression [ expression ]  
postfix-expression ( expression-list)  
simple-type-name ( expression-list)  
postfix-expression . name  
postfix-expression –> name  
postfix-expression ++  
postfix-expression ––  
cast-keyword < typename > (expression ) typeid ( typename )  
```  
  
 Der oben angegebene *postfix\-expression* kann ein primärer oder ein anderer Postfixausdruck sein.  Weitere Informationen erhalten Sie unter **primäre Ausdrücke**.  Postfixausdrücke gruppieren sich von links nach rechts und ermöglichen so das Verketten der Ausdrücke wie folgt:  
  
```  
func(1)->GetValue()++  
```  
  
 Im obigen Ausdruck ist "func" ein primärer Ausdruck, "func\(1\)" ist ein Funktions\-Postfixausdruck, "func\(1\)\-\>GetData" ist ein Postfixausdruck, der einen Member der Klasse angibt, "func\(1\)\>GetData\(\)" ist ein weiterer Funktions\-Postfixausdruck, und der gesamte Ausdruck ist ein Postfixausdruck, der den Rückgabewert von "GetData" erhöht.  Die Bedeutung des Ausdrucks als Ganzes ist "Funktion aufrufen, dabei 1 als Argument übergeben und einen Zeiger für eine Klasse als Rückgabewert erhalten.  Dann 'GetValue \(\)' für diese Klasse aufrufen und den zurückgegebenen Wert erhöhen."  
  
 Die oben aufgeführten Ausdrücke sind Zuweisungsausdrücke, was bedeutet, dass das Ergebnis dieser Ausdrücke ein "r\-value" sein muss.  
  
 Die Form des Postfixausdrucks  
  
```  
simple-type-name ( expression-list )  
```  
  
 gibt den Aufruf des Konstruktors an.  Wenn "simple\-type\-name" ein grundlegender Typ ist, muss die Ausdrucksliste ein einzelner Ausdruck sein, und dieser Ausdruck gibt eine Umwandlung des Werts des Ausdrucks in den einfachen Typ an.  Dieser Typ von Umwandlungsausdruck imitiert einen Konstruktor.  Da diese Form die Konstruktion grundlegender Klassen und Typen mit derselben Syntax ermöglicht, ist sie bei der Definition von Vorlagenklassen besonders nützlich.  
  
 Das *cast\-keyword* ist eines von `dynamic_cast`, `static_cast` oder `reinterpret_cast`.  Weitere Informationen finden Sie unter **dynamic\_cast**, **static\_cast** und **reinterpet\_cast**.  
  
 Der `typeid`\-Operator gilt als Postfixausdruck.  Weitere Informationen erhalten Sie unter **typeid\-Operator**.  
  
## Formale und tatsächliche Argumente  
 Aufrufende Programme übergeben Informationen an die aufgerufenen Funktionen in "tatsächlichen Argumenten". Die aufgerufenen Funktionen greifen mithilfe der entsprechenden "formalen Argumente" auf die Informationen zu.  
  
 Wenn eine Funktion aufgerufen wird, werden die folgenden Aufgaben ausgeführt:  
  
-   Alle tatsächlichen Argumente \(die vom Aufrufer angegebenen\) werden ausgewertet.  Es gibt keine implizite Reihenfolge, in der diese Argumente ausgewertet werden. Alle Argumente werden jedoch ausgewertet, und alle Nebeneffekte werden vor dem Eintritt in die Funktion abgeschlossen.  
  
-   Jedes formale Argument wird mit dem entsprechenden tatsächlichen Argument in der Ausdrucksliste initialisiert.  \(Ein formales Argument ist ein Argument, das im Funktionsheader deklariert und im Text einer Funktion verwendet wird.\) Konvertierungen werden wie durch Initialisierung ausgeführt. Sowohl Standard\- als auch benutzerdefinierte Konvertierungen werden beim Konvertieren eines tatsächlichen Arguments in den richtigen Typ ausgeführt.  Die ausgeführte Initialisierung wird durch den folgenden Code konzeptionell veranschaulicht:  
  
    ```  
    void Func( int i ); // Function prototype  
    ...  
    Func( 7 );          // Execute function call  
    ```  
  
     Die konzeptionellen Initialisierungen vor dem Aufruf sind:  
  
    ```  
    int Temp_i = 7;  
    Func( Temp_i );  
    ```  
  
     Beachten Sie, dass die Initialisierung ausgeführt wird, als würde die Gleichheitszeichensyntax anstelle der Klammersyntax verwendet werden.  Eine Kopie von `i` wird vor dem Übergeben des Werts an die Funktion erstellt.  \(Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md) und [Konvertierungen](../cpp/user-defined-type-conversions-cpp.md), [Initialisierung mithilfe spezieller Memberfunktionen](assetId:///82223d73-64cb-4923-b678-78f9568ff3ca) und [Explizite Initialisierung](assetId:///c89724f8-ddd3-4d77-b86d-77fcd8bd8595).\)  
  
     Wenn der Funktionsprototyp \(Deklaration\) daher ein Argument des Typs **long** aufruft und wenn das aufrufende Programm ein tatsächliches Argument des Typs `int` bereitstellt, wird das tatsächliche Argument mit einer Standardkonvertierung auf den Typ **long** erweitert \(siehe [Standardkonvertierungen](../cpp/standard-conversions.md)\).  
  
     Es ist ein Fehler, ein tatsächliches Argument anzugeben, für das es keine Standard\- oder benutzerdefinierte Konvertierung in den Typ des formalen Arguments gibt.  
  
     Für die tatsächlichen Argumente des Klassentyps wird das formale Argument initialisiert, indem der Konstruktor der Klasse aufgerufen wird.  \(Weitere Informationen über diese speziellen Klassenmemberfunktionen finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md).\)  
  
-   Der Funktionsaufruf wird ausgeführt.  
  
 Das folgende Programmfragment zeigt einen Funktionsaufruf:  
  
```  
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
  
 Wenn `func` aus Main aufgerufen wird, wird der formale Parameter `param1` mit dem Wert von `i` initialisiert \(`i` wird mithilfe einer Standardkonvertierung in den Typ **long** konvertiert, damit es dem richtigen Typ entspricht\), und der formale Parameter `param2` wird mit dem Wert von `j` initialisiert \(`j` wird mit einer Standardkonvertierung in den Typ **double** konvertiert\).  
  
## Behandlung von Argumenttypen  
 Formale Argumente, die als const\-Typen deklariert sind, können im Funktionstext nicht geändert werden.  Funktionen können jedes Argument ändern, das nicht vom Typ **const** ist.  Allerdings ist die Änderung auf die Funktion beschränkt und wirkt sich nicht auf den Wert des tatsächlichen Arguments aus, es sei denn, das tatsächliche Argument ist ein Verweis auf ein Objekt, das nicht den Typ **const** aufweist.  
  
 Die folgenden Funktionen veranschaulichen einige dieser Konzepte:  
  
```  
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
  
## Ellipsen und Standardargumente  
 Funktionen können deklariert werden, um weniger Argumente als in der Funktionsdefinition angegeben mit einer der folgenden beiden Methoden zu akzeptieren: Auslassungspunkte \(`...`\) oder Standardargumente.  
  
 Auslassungspunkte geben an, dass Argumente möglicherweise erforderlich sind, dass die Anzahl und Typen jedoch nicht in der Deklaration angegeben werden.  Dies ist normalerweise ein schlechtes Beispiel für C\+\+\-Programmierung, da es einen der Vorteile von C\+\+ unterlaufen kann: Typsicherheit.  Verschiedene Konvertierungen werden auf Funktionen angewendet, die mit Auslassungszeichen deklariert sind, und nicht auf jene Funktionen, deren formale und tatsächliche Argumenttypen bekannt sind:  
  
-   Wenn das tatsächliche Argument vom Typ **float** ist, wird es vor dem Funktionsaufruf auf den Typ **double** hochgestuft.  
  
-   Jeder `char`\-, **short**\-, enumerierte Typ bzw. jedes Bit\-Feld mit oder ohne Vorzeichen wird mittels ganzzahliger Heraufstufung in `int` mit oder ohne Vorzeichen konvertiert.  
  
-   Jedes Argument des Klassentyps wird durch einen Wert als Datenstruktur übergeben; die Kopie wird durch Kopieren der Binärdatei statt durch Aufrufen des Kopierkonstruktors der Klasse erstellt \(falls vorhanden\).  
  
 Ellipsen müssen in der Argumentliste zuletzt deklariert werden, sofern sie vorhanden sind.  Weitere Informationen zum Übergeben einer variablen Anzahl von Argumenten finden Sie in den Ausführungen zu [va\_arg, va\_start und va\_list](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) in der *Laufzeitbibliotheksreferenz*.  
  
 Weitere Informationen zu Standardargumenten in der CLR\-Programmierung finden Sie unter [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
 Mit Standardargumenten können Sie den Wert festlegen, den ein Argument annehmen soll, wenn keiner im Funktionsaufruf angegeben wird.  Das folgende Codefragment zeigt, wie Standardargumente funktionieren.  Weitere Informationen zu Einschränkungen beim Festlegen von Standardargumenten, finden Sie unter [Standardargumente](../cpp/default-arguments.md).  
  
```  
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
  
 Das vorangehende Programm deklariert eine Funktion, `print`, die zwei Argumente akzeptiert.  Das zweite Argument, `terminator`, weist jedoch einen Standardwert, `"\n"`, auf.  In **main** ermöglichen die ersten beiden Aufrufe von `print` dem zweiten Standardargument die Bereitstellung einer neuen Zeile, um die gedruckte Zeichenfolge zu beenden.  Der dritte Aufruf gibt einen expliziten Wert für das zweite Argument zurück.  Die Ausgabe des Programms lautet  
  
```  
hello,  
world!  
good morning, sunshine.  
```  
  
## Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)