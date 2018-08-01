---
title: Übersicht über Deklaratoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f09df81587012703d8ba1fc883413d6d35929e8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404937"
---
# <a name="overview-of-declarators"></a>Übersicht über Deklaratoren
Deklaratoren sind die Komponenten einer Deklaration, die Namen von Objekten oder Funktionen angeben. Deklaratoren geben auch an, ob das benannte Objekt ein Objekt, ein Zeiger, ein Verweis oder ein Array ist.  Obwohl Deklaratoren nicht den Basistyp angeben, ändern sie die Typinformationen im Basistyp, sodass dieser abgeleitete Typen, wie Zeiger, Verweise und Arrays, angibt.  Auf Funktionen angewendet arbeitet der Deklarator mit dem Typspezifizierer, um den Rückgabetyp einer Funktion vollständig als Objekt, Zeiger oder Verweis anzugeben. (Bezeichner, die in beschriebenen [Deklarationen und Definitionen](declarations-and-definitions-cpp.md), übermitteln Eigenschaften, z. B. Typ und Speicherklasse. Modifizierer, erläutert in diesem Abschnitt und in [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md), ändern Deklaratoren.) Die folgende Abbildung zeigt eine vollständige Deklaration von `MyFunction` und ruft die Komponenten der Deklaration auf.  
  
 ![Modifizierer, Spezifizierer und Deklaratoren](../cpp/media/vc38qy1.gif "vc38QY1")  
Bezeichner, Modifizierer und Deklaratoren  
  
 **Microsoft-spezifisch**  
  
 Die meisten erweiterten Microsoft-Schlüsselwörter können als Modifizierer verwendet werden, um abgeleitete Typen zu bilden. Dabei handelt es sich nicht um Spezifizierer oder Deklaratoren. (Finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).)  
  
 **Ende Microsoft-spezifisch**  
  
 Deklaratoren erscheinen in der Syntax für Deklarationen nach einer optionalen Liste mit Spezifizierern. Diese Bezeichner finden Sie im [Deklarationen.](declarations-and-definitions-cpp.md) Eine Deklaration kann mehr als einen Deklarator enthalten, aber jeder Deklarator deklariert nur einen Namen.  
  
 Die folgende Beispieldeklaration zeigt, wie Spezifizierer und Deklaratoren kombiniert werden, um eine vollständige Deklaration zu bilden:  
  
```cpp 
const char *pch, ch;  
```  
  
 In der vorherigen Deklaration, die Schlüsselwörter **const** und **Char** bilden die Liste der Spezifizierer. Zwei Deklaratoren werden aufgeführt: `*pch` und `ch`.  Eine Deklaration, die mehrere Entitäten deklariert, besteht aus einem Typspezifizierer, der von einer durch Trennzeichen getrennten Liste von Deklaratoren gefolgt wird, mit einem Semikolon am Ende.  
  
 **Deklaratoren für einfache Objekte**  
  
 Der Deklarator eines einfachen Objekts, z. B. "int" oder "double", ist einfach nur sein Namen mit optionalen Klammern.  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **Deklaratoren für Zeiger, Verweise und Arrays**  
  
 Zeigeroperatoren, die vor dem Namen eingefügt werden, bewirken, dass das Objekt zu einem Zeiger oder Verweis wird.  Die **\*** -Operator deklariert den Namen als Zeiger, der **&** -Operator deklariert ihn als Verweis.  
  
```cpp 
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 Anfügen von **const** oder **flüchtige** erhält der Zeiger diese speziellen Eigenschaften.  Die Verwendung dieser Spezifizierer in einen Deklarator (im Gegensatz zur Verwendung im Typspezifizierer) ändert die Eigenschaften des Zeigers, nicht die des Objekts, auf das gezeigt wird:  
  
```cpp 
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 Weitere Informationen finden Sie im [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md).  
  
 Ein Zeiger auf einen Member einer Klasse oder Struktur wird mit dem entsprechenden geschachtelten Namenspezifizierer deklariert:  
  
```cpp 
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 Durch Klammern, die einen optionalen konstanten Ausdruck nach dem Namen einschließen, wird das Objekt zu einem Array.  Aufeinander folgende Klammern deklarieren zusätzliche Dimensionen für das Array.  
  
```cpp 
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **Deklaratoren für Funktionen**  
  
 Klammern, die die Argumentliste enthalten, werden nach dem Namen zum Deklarieren einer Funktion verwendet.  Das folgende Beispiel deklariert eine Funktion eines Rückgabetyps **Int** und drei Argumente des Typs **Int**.  
  
```cpp 
int f(int a, int b, int c);  
```  
  
 Zeiger und Verweise auf Funktionen werden deklariert, indem Sie den Zeiger- oder Verweisoperator dem Funktionsnamen wie unten dargestellt voranstellen.  Klammern, die normalerweise optional sind, sind erforderlich, um einen Zeiger auf eine Funktion von einer Funktion zu unterscheiden, die einen Zeiger zurückgibt:  
  
```cpp 
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 Zeiger auf Memberfunktionen zeichnen sich durch geschachtelte Namensspezifizierer aus:  
  
```cpp 
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 Siehe auch [Zeiger auf Member](../cpp/pointers-to-members.md).  
  
 **Funktionen und Objekte in der gleichen Deklaration**  
  
 Funktionen und Objekte können in der gleichen Deklaration wie folgt deklariert werden:  
  
```cpp 
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 Die Syntax kann unter bestimmten Umständen irreführend sein.  Die folgende Deklarierung  
  
```cpp 
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 sieht möglicherweise wie die Deklaration einer **Int** Zeiger und eine Funktion zurückgibt `int*`, aber nicht.  Der Grund dafür ist die \* ist Teil des Deklarators für `i`, nicht Teil des Deklarators für `f`.  
  
 **Vereinfachung der deklaratorsyntax mit typedef**  
  
 Ist eine bessere Methode besteht jedoch die Verwendung einer **Typedef** oder eine Kombination aus Klammern und **Typedef** Schlüsselwort. Erwägen Sie, ein Array von Zeigern auf Funktionen zu deklarieren:  
  
```cpp 
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 Die entsprechende Deklaration geschrieben werden kann, ohne die **Typedef** Deklaration, es ist jedoch so kompliziert, dass das fehlerpotential jeden nutzen übertrifft:  
  
```cpp 
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Weitere Informationen zu Typedef finden Sie unter [Aliase und Typedefs](aliases-and-typedefs-cpp.md).  
  
 Zeiger, Verweise und Arrays eines einzelnen Basistyps können in einer einzigen Deklaration (durch Trennzeichen getrennt) zu Folgendem kombiniert werden:  
  
```cpp 
int a, *b, c[5], **d, &e=a;  
```  
  
 **Komplexere deklaratorsyntax**  
  
- Zeiger-, Verweis-, Array- und Funktionsdeklaratoren werden möglicherweise kombiniert, um diese Objekte als Arrays von Zeigern auf Funktionen, Zeigern auf Arrays usw. anzugeben.  
  
- Die folgende rekursive Grammatik beschreibt die Zeigerdeklaratorsyntax vollständig.  
  
- Ein `declarator` wird definiert als einer von:  

  - identifier   
  - Vollständiger name   
  - der Deklarator (Argumentliste) [cv-Qualfiers] [-Ausnahme-Spezifikation]  
  - Deklarator [[Konstantenausdruck]]
  - Zeiger-Operator Deklarator   
  - (Deklarator)  

- und *Zeiger-Operator* ist einer der:  
  
  - \* [cv-Qualifizierer]  
  - & [cv-Qualifizierer]:: geschachtelten namesspezifizierer \* [cv-Qualifizierer]  

 Da ein Deklarator Deklaratoren enthalten kann, ist es möglich, anhand der oben genannten Regeln komplexere abgeleitete Typen zu erstellen (z. B. Arrays von Zeigern, Funktionen, die Arrays von Funktionszeigern zurückgeben).  Um die einzelnen Schritte der Konstruktion zu bilden, beginnen Sie mit dem Bezeichner, der den Basisdatentyp darstellt, und wenden Sie die Syntaxregel oben mit dem vorherigen Ausdruck als `declarator` an.  Die Anwendung der Syntaxregeln sollte der umgekehrten Reihenfolge des Ausdrucks auf Englisch entsprechen.  Wenn die Anwendung die *Zeiger-Operator* -Syntaxregel auf einen Array- oder Funktionsausdruck, verwenden Sie Klammern, wenn einen Zeiger auf das Array oder eine Funktion, wie die letzte Zeile in der folgenden Tabelle werden sollen.  
  
 Das folgende Beispiel zeigt die Konstruktion von "Zeiger zu Array von 10 Zeigern zu int".  
  
|Verbaler Ausdruck|Deklarator|Angewendete Syntaxregel|  
|-----------------------|----------------|-------------------------|  
||`i`|1|  
|Zeiger auf|`*i`|5|  
|Array von 10|`(*i)[10]`|4|  
|Zeiger auf|`*((*i)[10])`|6 und anschließend 5|  
  
 Wenn mehrere Zeiger-, Verweis-, Array- oder Funktionsmodifizierer verwendet werden, werden Deklaratoren möglicherweise recht kompliziert.  Das Thema [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md) beschreibt, wie Sie die Syntax komplexeren Deklaratoren gelesen.  Das Thema gilt für C- und C++, obwohl in C++ die \* zeigt an, ein Zeiger ist, ein qualifizierter Name wie beispielsweise MyClass::\* kann verwendet werden, um einen Zeiger auf einen Member einer Klasse angeben.