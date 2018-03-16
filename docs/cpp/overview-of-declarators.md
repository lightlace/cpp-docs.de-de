---
title: "Übersicht über Deklaratoren | Microsoft Docs"
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
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18a3f12ac87f0165c74aaa487913f679f1a9941e
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="overview-of-declarators"></a>Übersicht über Deklaratoren
Deklaratoren sind die Komponenten einer Deklaration, die Namen von Objekten oder Funktionen angeben. Deklaratoren geben auch an, ob das benannte Objekt ein Objekt, ein Zeiger, ein Verweis oder ein Array ist.  Obwohl Deklaratoren nicht den Basistyp angeben, ändern sie die Typinformationen im Basistyp, sodass dieser abgeleitete Typen, wie Zeiger, Verweise und Arrays, angibt.  Auf Funktionen angewendet arbeitet der Deklarator mit dem Typspezifizierer, um den Rückgabetyp einer Funktion vollständig als Objekt, Zeiger oder Verweis anzugeben. (Bezeichner, die in beschriebenen [Deklarationen und Definitionen](declarations-and-definitions-cpp.md), übermitteln Eigenschaften, wie Typ und Speicherklasse. Modifizierer, erläutert in diesem Abschnitt und in [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md), ändern Deklaratoren.) Die folgende Abbildung zeigt eine vollständige Deklaration von `MyFunction` und ruft die Komponenten der Deklaration auf.  
  
 ![Modifizierer, Spezifizierer und Deklaratoren](../cpp/media/vc38qy1.gif "vc38QY1")  
Bezeichner, Modifizierer und Deklaratoren  
  
 **Microsoft-spezifisch**  
  
 Die meisten erweiterten Microsoft-Schlüsselwörter können als Modifizierer verwendet werden, um abgeleitete Typen zu bilden. Dabei handelt es sich nicht um Spezifizierer oder Deklaratoren. (Siehe [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).)  
  
 **Ende Microsoft-spezifisch**  
  
 Deklaratoren erscheinen in der Syntax für Deklarationen nach einer optionalen Liste mit Spezifizierern. Diese Spezifizierer werden in erläutert [Deklarationen.](declarations-and-definitions-cpp.md) Eine Deklaration kann mehr als einen Deklarator enthalten, aber jeder Deklarator deklariert nur einen Namen.  
  
 Die folgende Beispieldeklaration zeigt, wie Spezifizierer und Deklaratoren kombiniert werden, um eine vollständige Deklaration zu bilden:  
  
```  
const char *pch, ch;  
```  
  
 In der vorherigen Deklaration, die Schlüsselwörter **const** und `char` bilden die Liste der Spezifizierer. Zwei Deklaratoren werden aufgeführt: `*pch` und `ch`.  Eine Deklaration, die mehrere Entitäten deklariert, besteht aus einem Typspezifizierer, der von einer durch Trennzeichen getrennten Liste von Deklaratoren gefolgt wird, mit einem Semikolon am Ende.  
  
 **Deklaratoren für einfache Objekte**  
  
 Der Deklarator eines einfachen Objekts, z. B. "int" oder "double", ist einfach nur sein Namen mit optionalen Klammern.  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **Deklaratoren für Zeiger, Verweise und Arrays**  
  
 Zeigeroperatoren, die vor dem Namen eingefügt werden, bewirken, dass das Objekt zu einem Zeiger oder Verweis wird.  Die  **\***  -Operator deklariert den Namen als Zeiger, der  **&**  -Operator deklariert ihn als Verweis.  
  
```  
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 Durch Anhängen von `const` oder `volatile` erhält der Zeiger diese speziellen Eigenschaften.  Die Verwendung dieser Spezifizierer in einen Deklarator (im Gegensatz zur Verwendung im Typspezifizierer) ändert die Eigenschaften des Zeigers, nicht die des Objekts, auf das gezeigt wird:  
  
```  
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 Weitere Informationen finden Sie [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md).  
  
 Ein Zeiger auf einen Member einer Klasse oder Struktur wird mit dem entsprechenden geschachtelten Namenspezifizierer deklariert:  
  
```  
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 Durch Klammern, die einen optionalen konstanten Ausdruck nach dem Namen einschließen, wird das Objekt zu einem Array.  Aufeinander folgende Klammern deklarieren zusätzliche Dimensionen für das Array.  
  
```  
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **Deklaratoren für Funktionen**  
  
 Klammern, die die Argumentliste enthalten, werden nach dem Namen zum Deklarieren einer Funktion verwendet.  Im Folgenden werden eine Funktion eines Rückgabetyps `int` und drei Argumente des Typs `int` deklariert.  
  
```  
int f(int a, int b, int c);  
```  
  
 Zeiger und Verweise auf Funktionen werden deklariert, indem Sie den Zeiger- oder Verweisoperator dem Funktionsnamen wie unten dargestellt voranstellen.  Klammern, die normalerweise optional sind, sind erforderlich, um einen Zeiger auf eine Funktion von einer Funktion zu unterscheiden, die einen Zeiger zurückgibt:  
  
```  
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 Zeiger auf Memberfunktionen zeichnen sich durch geschachtelte Namensspezifizierer aus:  
  
```  
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 Siehe auch [Zeiger auf Member](../cpp/pointers-to-members.md).  
  
 **Funktionen und Objekte in der gleichen Deklaration**  
  
 Funktionen und Objekte können in der gleichen Deklaration wie folgt deklariert werden:  
  
```  
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 Die Syntax kann unter bestimmten Umständen irreführend sein.  Die folgende Deklarierung  
  
```  
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 sieht möglicherweise aus wie die Deklaration eines `int`-Zeigers und einer Funktion, die `int*` zurückgibt, ist es aber nicht.  Das liegt daran, dass * Bestandteil des Deklarators für `i` und nicht Teil des Deklarators für `f` ist.  
  
 **Vereinfachung der deklaratorsyntax mit typedef**  
  
 Eine bessere Methode besteht jedoch darin, ein `typedef`-Schlüsselwort oder eine Kombination aus Klammern und `typedef`-Schlüsselwort zu verwenden. Erwägen Sie, ein Array von Zeigern auf Funktionen zu deklarieren:  
  
```  
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 Die entsprechende Deklaration kann ohne die `typedef`-Deklaration geschrieben werden, aber dies ist so kompliziert, dass das Fehlerpotential jeden Nutzen übertrifft:  
  
```  
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Weitere Informationen zu Typedef finden Sie unter [Aliase und Typedefs](aliases-and-typedefs-cpp.md).  
  
 Zeiger, Verweise und Arrays eines einzelnen Basistyps können in einer einzigen Deklaration (durch Trennzeichen getrennt) zu Folgendem kombiniert werden:  
  
```  
int a, *b, c[5], **d, &e=a;  
```  
  
 **Komplexere deklaratorsyntax**  
  
-   Zeiger-, Verweis-, Array- und Funktionsdeklaratoren werden möglicherweise kombiniert, um diese Objekte als Arrays von Zeigern auf Funktionen, Zeigern auf Arrays usw. anzugeben.  
  
-   Die folgende rekursive Grammatik beschreibt die Zeigerdeklaratorsyntax vollständig.  
  
-   Ein `declarator` wird definiert als einer von:  
  
```  
1. identifier   
2. qualified-name   
3. declarator ( argument-list ) [cv-qualfiers] [exception-spec]  
4. declarator [ [ constant-expression ] ]   
  
5. pointer-operatordeclarator   
6. ( declarator )  
```  
  
-   und *Zeiger-Operator* ist einer von:  
  
```  
  
      * [cv-qualifiers]  
& [cv-qualifiers]  
::nested-name-specifier * [cv-qualfiers]  
```  
  
 Da ein Deklarator Deklaratoren enthalten kann, ist es möglich, anhand der oben genannten Regeln komplexere abgeleitete Typen zu erstellen (z. B. Arrays von Zeigern, Funktionen, die Arrays von Funktionszeigern zurückgeben).  Um die einzelnen Schritte der Konstruktion zu bilden, beginnen Sie mit dem Bezeichner, der den Basisdatentyp darstellt, und wenden Sie die Syntaxregel oben mit dem vorherigen Ausdruck als `declarator` an.  Die Anwendung der Syntaxregeln sollte der umgekehrten Reihenfolge des Ausdrucks auf Englisch entsprechen.  Wenn Anwenden der *Zeiger-Operator* -Syntaxregel auf einen Array- oder Funktionsausdruck, verwenden Sie Klammern, wenn Sie einen Zeiger auf das Array oder eine Funktion, wie in der letzten Zeile in der folgenden Tabelle werden soll.  
  
 Das folgende Beispiel zeigt die Konstruktion von "Zeiger zu Array von 10 Zeigern zu int".  
  
|Verbaler Ausdruck|Deklarator|Angewendete Syntaxregel|  
|-----------------------|----------------|-------------------------|  
||`i`|1|  
|Zeiger auf|`*i`|5|  
|Array von 10|`(*i)[10]`|4|  
|Zeiger auf|`*((*i)[10])`|6 und anschließend 5|  
  
 Wenn mehrere Zeiger-, Verweis-, Array- oder Funktionsmodifizierer verwendet werden, werden Deklaratoren möglicherweise recht kompliziert.  Das Thema [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md) beschreibt die Syntax komplexeren Deklaratoren gelesen.  Das Thema trifft auf C und C++, obwohl in C++ ist der * wird verwendet, um anzugeben, einen Zeiger ist ein qualifizierter Name wie beispielsweise MyClass::\* kann verwendet werden, um einen Zeiger auf einen Member einer Klasse angeben.