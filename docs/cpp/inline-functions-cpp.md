---
title: "Inlinefunktionen"
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
  - "__forceinline_cpp"
  - "__inline_cpp"
  - "inline_cpp"
  - "__forceinline"
  - "__inline"
  - "inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinefunktionen, Klassenmember"
ms.assetid: 355f120c-2847-4608-ac04-8dda18ffe10c
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Inlinefunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Funktion, die im Text einer Klassendeklaration definiert ist, ist eine Inlinefunktion.  
  
## Beispiel  
 In der folgenden Klassendeklaration ist der `Account`\-Konstruktor eine Inlinefunktion.  Die Memberfunktionen `GetBalance`, `Deposit` und `Withdraw` sind nicht als **inline** festgelegt, können aber als Inlinefunktion implementiert werden.  
  
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
>  In der Klassendeklaration wurden die Funktionen ohne das **inline**\-Schlüsselwort deklariert.  Das Schlüsselwort **inline** kann in der Klassendeklaration bezeichnet werden; das Ergebnis ist dasselbe.  
  
 Eine angegebene Inlinememberfunktion muss in jeder Kompilierungseinheit auf die gleiche Weise deklariert werden.  Diese Einschränkung bewirkt, dass sich Inlinefunktionen wie instanziierte Funktionen verhalten.  Außerdem muss es genau eine Definition einer Inlinefunktion geben.  
  
 Eine Klassenmemberfunktion führt standardmäßig zu externer Bindung, es sei denn, eine Definition für diese Funktion enthält den **inline**\-Spezifizierer.  Das vorhergehende Beispiel zeigt, dass diese Funktionen nicht explizit mit dem **inline**\-Spezifizierer deklariert werden müssen. Die Verwendung von **inline** in der Funktionsdefinition bedeutet bereits, dass es sich um eine Inlinefunktion handelt.  Es ist jedoch nicht zulässig, eine Funktion nach einem Aufruf als **inline** zu redeklarieren.  
  
## „Inline“, „\_\_inline“ und „\_\_forceinline“  
 Die Spezifizierer `inline` und `__inline` weisen den Compiler an, eine Kopie des Funktionstexts an jeder Stelle einzufügen, an der die Funktion aufgerufen wird.  
  
 Die Einfügung \(bezeichnet als Inlineerweiterung oder Inlinekonstrukt\) wird nur ausgeführt, wenn die Kosten\-Nutzen\-Analyse des Compilers dies als sinnvoll bewertet.  Eine Inlineerweiterung verringert den Funktionsaufruf\-Mehraufwand, möglicherweise auf Kosten der größeren Codegröße.  
  
 Das `__forceinline`\-Schlüsselwort überschreibt die Kosten\-Nutzen\-Analyse und basiert stattdessen auf dem Urteil des Programmierers.  Sie sollten `__forceinline` mit Vorsicht verwenden.  Die wahllose Verwendung von `__forceinline` kann zu längerem Code mit nur marginalen Leistungssteigerungen oder in einigen Fällen sogar mit Leistungsverlusten führen \(beispielsweise aufgrund des erweiterten Pagings einer größeren ausführbaren Datei\).  
  
 Die Verwendung von Inlinefunktionen kann das Programm schneller machen, da so der Mehraufwand vermieden wird, der Funktionsaufrufen zugeordnet ist.  Inline erweiterte Funktionen unterliegen Codeoptimierungen, die für normale Funktionen nicht verfügbar sind.  
  
 Der Compiler behandelt die Inlineerweiterungsoptionen und \-Schlüsselwörter als Vorschläge.  Es gibt keine Garantie, dass Funktionen inline gestellt werden.  Sie können den Compiler nicht zwingen, eine bestimmte Funktion inline zu setzen, auch nicht mit dem `__forceinline`\-Schlüsselwort.  Beim Kompilieren mit **\/clr** setzt der Compiler eine Funktion nicht inline, wenn auf die Funktion Sicherheitsattribute angewendet werden.  
  
 Das **inline**\-Schlüsselwort ist nur in C\+\+ verfügbar.  Die Schlüsselwörter `__inline` und `__forceinline` sind sowohl in C als auch in C\+\+ verfügbar.  Aus Gründen der Kompatibilität mit früheren Versionen ist **\_inline** ein Synonym für `__inline`.  
  
 Das Schlüsselwort **inline** teilt dem Compiler mit, dass eine Inlineerweiterung bevorzugt wird.  Jedoch kann der Compiler eine separate Instanz der Funktion erstellen \(instanziieren\) und Standardaufrufbindungen erstellen, anstatt den Code inline einzufügen.  Zwei Fälle, in denen dies auftreten kann, sind:  
  
-   Rekursive Funktionen.  
  
-   Funktionen, auf die durch einen Zeiger an anderer Stelle in der Übersetzungseinheit verwiesen wird.  
  
 Diese Gründe beeinträchtigen möglicherweise Inlinekonstrukte, *wie ggf. auch andere*, je nach Compilereinstellung. Sie sollten nicht vom **inline**\-Spezifizierer abhängen, um eine Funktion inline zu setzen.  
  
 Wie bei normalen Funktionen so ist auch bei den Argumenten einer Inlinefunktion die Reihenfolge der Auswertung nicht festgelegt.  Tatsächlich kann sie sich von der Reihenfolge unterscheiden, in der die Argumente ausgewertet werden, wenn sie mithilfe des normalen Funktionsaufrufprotokolls übergeben werden.  
  
 Mit der [\/Ob](../build/reference/ob-inline-function-expansion.md)\-Compileroptimierungsoption kann bestimmt werden, ob die Inlinefunktionserweiterung tatsächlich stattfindet.  
  
 [\/LTCG](../build/reference/ltcg-link-time-code-generation.md) führt modulübergreifende Inlinekonstrukte aus, unabhängig davon, ob dies im Quellcode angefordert wurde.  
  
### Beispiel 1  
  
```  
// inline_keyword1.cpp  
// compile with: /c  
inline int max( int a , int b ) {  
   if( a > b )   
      return a;  
   return b;  
}  
```  
  
 Die Memberfunktionen einer Klasse können inline deklariert werden, entweder indem das **inline**\-Schlüsselwort verwendet oder die Funktionsdefinition innerhalb der Klassendefinition platziert wird.  
  
### Beispiel 2  
  
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
  
### Microsoft\-spezifisch  
 Das `__inline`\-Schlüsselwort ist äquivalent zu **inline**.  
  
 Auch mit `__forceinline` kann der Compiler Code nicht in allen Fällen inline setzen.  Der Compiler kann keine Funktion inline setzen, wenn Folgendes der Fall ist:  
  
-   Die Funktion oder ihr Aufrufer werden mit \/Ob0 kompiliert \(die Standardoption für Debugbuilds\).  
  
-   Die Funktion und der Aufrufer verwenden unterschiedliche Typen der Ausnahmebehandlung \(C\+\+\-Ausnahmebehandlung zum einen, strukturierte Ausnahmebehandlung zum anderen\).  
  
-   Die Funktion weist eine variable Argumentliste auf.  
  
-   Die Funktion verwendet eine Inlineassembly, es sei denn, sie wird mit \/Og, \/Ox, \/O1, oder \/O2 kompiliert.  
  
-   Die Funktion ist rekursiv und geht nicht mit **\#pragma inline\_recursion\(on\)** einher.  Mit dem Pragma werden rekursive Funktionen mit einer Standardtiefe von 16 Aufrufen inline gesetzt.  Um die Tiefe bei Inlinekonstrukten zu reduzieren, verwenden Sie das [inline\_depth](../preprocessor/inline-depth.md)\-Pragma.  
  
-   Die Funktion ist virtuell und wird virtuell aufgerufen.  Direkte Aufrufe virtueller Funktionen können inline gesetzt werden.  
  
-   Das Programm akzeptiert die Adresse der Funktion, und der Aufruf erfolgt über den Zeiger auf die Funktion.  Direkte Aufrufe von Funktionen, deren Adresse akzeptiert wurden, können inline gesetzt werden.  
  
-   Die Funktion wird auch mit dem [naked](../cpp/naked-cpp.md) [\_\_declspec](../cpp/declspec.md)\-Modifizierer gekennzeichnet.  
  
 Wenn der Compiler eine Funktion, die mit `__forceinline` deklariert ist, nicht inline stellen kann, wird eine Warnung der Stufe 1 ausgelöst.  
  
 Rekursive Funktionen können inline ersetzt werden, mit einer vom [inline\_depth](../preprocessor/inline-depth.md)\-Pragma angegebenen Tiefe von bis zu maximal 16 Aufrufen.  Nach dieser Tiefe werden rekursive Funktionsaufrufe als Aufrufe einer Instanz der Funktion behandelt.  Die Tiefe, bis zu der rekursive Funktionen durch die Inlineheuristik geprüft werden, kann 16 nicht überschreiten.  Das [inline\_recursion](../preprocessor/inline-recursion.md)\-Pragma steuert die Inlineerweiterung einer Funktion, die aktuell erweitert wird.  Weitere Informationen erhalten Sie unter der \(\/Ob\)\-Compileroption [Inlinefunktionserweiterung](../build/reference/ob-inline-function-expansion.md).  
  
### Ende Microsoft\-spezifisch  
 Weitere Informationen zum Verwenden des **inline**\-Bezeichners finden Sie unter:  
  
-   [Inline\-Klassenmemberfunktionen](../cpp/inline-functions-cpp.md)  
  
-   [Inlinefunktionen im Vergleich zu Makros](../misc/inline-functions-versus-macros.md)  
  
-   [Verwendungsmöglichkeiten von Inlinefunktionen](../misc/when-to-use-inline-functions.md)  
  
-   [Definieren von C\+\+\-Inlinefunktionen mit dllexport und dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
## Verwendungsmöglichkeiten von Inlinefunktionen  
 Inlinefunktionen werden am besten für kleine Funktionen verwendet, z. B. Zugriff auf private Datenmember.  Ein\- oder zweispurige "Accessor"\-Funktionen geben in erster Linie Zustandsinformationen über Objekte ab. Kurze Funktionen werden von der Restkapazität des Funktionsaufrufs beeinflusst.  Längere Funktionen benötigen proportional weniger Zeit in der Aufruf\-\/Rückgabesequenz und profitieren weniger vom Inlining.  
  
 Die `Point`\-Klasse, die in [Funktionsaufrufergebnisse](../misc/function-call-results.md) eingeführt wird, kann wie nachfolgend veranschaulicht optimiert werden:  
  
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
  
 Die Koordinatenmanipulation ist ein relativ allgemeiner Vorgang in einem Client dieser Klasse und durch die Angabe der beiden Accessorfunktionen \(`x` und `y` im vorhergehenden Beispiel\) als **inline** wird in der Regel der Mehraufwand gespart bei:  
  
-   Funktionsaufrufen \(einschließlich der Parameterübergabe und \-ablage der Adresse des Objekts auf dem Stapel\)  
  
-   Beibehaltung des Stapelrahmens des Aufrufers  
  
-   Neuem Stapelrahmensetup  
  
-   Rückgabewertkommunikation  
  
-   Wiederherstellung des alten Stapelrahmens  
  
-   Zurück  
  
## Inlinefunktionen im Vergleich mitMakros  
 Obwohl Inlinefunktionen Makros ähneln \(da der Funktionscode zum Zeitpunkt des Aufrufs zur Kompilierzeit erweitert wird\), werden Inlinefunktionen vom Compiler analysiert, während Makros vom Präprozessor erweitert werden.  Folglich gibt es einige wichtige Unterschiede:  
  
-   Inlinefunktionen folgen allen Protokollen des Typs mit erzwungener Sicherheit auf normalen Funktionen.  
  
-   Inlinefunktionen werden mit derselben Syntax wie jede andere Funktion angegeben, allerdings ist das **inline**\-Schlüsselwort in der Funktionsdeklaration enthalten.  
  
-   Die Ausdrücke, die als Argumente an Inlinefunktionen übergeben werden, werden einmal ausgewertet.  In einigen Fällen können die Ausdrücke, die als Argumente an Makros übergeben werden, mehrmals ausgewertet werden.  
  
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
  
 Der Zweck des Ausdrucks `toupper(getc(stdin))` ist, dass ein Zeichen aus der Konsole \(`stdin`\) gelesen und bei Bedarf in Großbuchstaben konvertiert werden soll.  
  
 Aufgrund der Implementierung des Makros wird `getc` einmal ausgeführt, um zu bestimmen, ob das Zeichen größer oder gleich "a" ist, und einmal, um zu bestimmen, ob es ist kleiner oder gleich "z" ist. Wenn es sich in diesem Bereich befindet, wird `getc` erneut ausgeführt, um das Zeichen in einen Großbuchstaben zu konvertieren.  Dies bedeutet, dass das Programm auf zwei oder drei Zeichen wartet, obwohl es idealerweise nur auf eines warten sollte.  
  
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
  
  **Beispieleingabe: `a`**   
 **Beispielausgabe: `A`**    
## Siehe auch  
 [noinline](../cpp/noinline.md)   
 [auto\_inline](../preprocessor/auto-inline.md)