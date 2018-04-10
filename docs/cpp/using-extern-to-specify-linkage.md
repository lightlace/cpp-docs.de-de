---
title: Mithilfe von "extern" zur Angabe der Verknüpfung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db93feb8c8fad13cf8de082858e68b89f93b5323
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-extern-to-specify-linkage"></a>Verwenden von "extern" zur Angabe der Verknüpfung
## <a name="syntax"></a>Syntax  
  
```  
  
      extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort `extern` deklariert eine Variable oder Funktion und gibt an, dass sie eine externe Verknüpfung hat (Ihr Name ist von Dateien aus sichtbar, mit Ausnahme der Datei, in der sie definiert wurde). Wenn eine Variable geändert wird, gibt `extern` an, dass die Variable eine statische Dauer hat (sie wird zugeordnet, wenn das Programm beginnt, und die Zuordnung wird aufgehoben, wenn das Programm beendet wird). Die Variable oder Funktion können in einer anderen Quelldatei oder später in derselben Datei definiert werden. Deklarationen von Variablen und Funktionen im Dateigültigkeitsbereich sind standardmäßig extern.  
  
## <a name="example"></a>Beispiel  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 Wenn sie mit einer Zeichenfolge verwendet wird, gibt `extern` in C++ an, dass die Bindungskonventionen einer anderen Sprache für die Deklaratoren verwendet werden. Auf C-Funktionen und - Daten kann nur dann zugegriffen werden, wenn sie zuvor wie eine C-Bindung deklariert wurden. Allerdings müssen sie in einer separat kompilierten Übersetzungseinheit definiert sein.  
  
 Microsoft C++ unterstützt die Zeichenfolgen **"C"** und **"C++"** in der *Zeichenfolgenliteral* Feld. Alle Standardincludedateien verwenden die Syntax `extern` "C", um die in C++-Programmen verwendeten Laufzeitbibliotheksfunktionen verwenden zu können.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt unterschiedliche Methoden, um Namen zu deklarieren, die eine C-Verknüpfung haben:  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 Wenn eine Funktion über mehr als eine Verknüpfungsspezifikation verfügt, müssen sie übereinstimmen. Es ist ein Fehler, Funktionen sowohl mit C- als auch mit C++-Bindung zu deklarieren. Wenn darüber hinaus zwei Deklarationen für eine Funktion in einem Programm auftreten – eine mit einer Verknüpfungsspezifikation und eine ohne – muss die Deklaration mit der Verknüpfungsspezifikation die erste sein. Alle redundanten Deklarationen von Funktionen, die bereits eine Verknüpfungsspezifikation haben, erhalten die in der ersten Deklaration angegebene Bindung. Zum Beispiel:  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 Funktionen und Objekte explizit deklariert als **statische** im Hauptteil eines zusammengesetzten bindungsspezifizierers (**{}**) werden als statische Funktionen oder Objekte behandelt der Bindungsspezifizierer wird ignoriert. Andere Funktionen und Objekte verhalten sich so, als wären sie unter Verwendung des `extern`-Schlüsselworts deklariert worden. (Finden Sie unter [mithilfe von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md) ausführliche Informationen zu den `extern` Schlüsselwort.)  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Speicherklassenspezifizierer "extern" "](../c-language/extern-storage-class-specifier.md)   
 [Verhalten von Bezeichnern](../c-language/behavior-of-identifiers.md)   
 [Verknüpfung](../c-language/linkage.md)