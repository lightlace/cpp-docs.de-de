---
title: neue "und" delete | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- delete_cpp
- new
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3af862988502ac0d1908c466aae5e62b753509c2
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="new-and-delete-operators"></a>Operatoren "new" und "delete"

C++ unterstützt die dynamische Zuordnung und Freigabe von Objekten mit dem [neue](../cpp/new-operator-cpp.md) und [löschen](../cpp/delete-operator-cpp.md) Operatoren. Diese Operatoren belegen Speicher für Objekte aus einem Pool, der als freier Speicher bezeichnet wird. Die `new` Operator Ruft die Spezialfunktion [new-Operator](../cpp/new-operator-cpp.md), und die `delete` Operator Ruft die Spezialfunktion [Delete-Operator](../cpp/delete-operator-cpp.md).  
  
 Die `new` -Funktion in der C++-Standardbibliothek unterstützt das Verhalten in der C++-Standard, d. eine Std:: bad_alloc-Ausnahme auslösen h., wenn die speicherbelegung fehlschlägt. Falls Sie weiterhin die nicht auslösende Version von benötigen `new`, das Programm mit nothrownew.obj verknüpfen. Jedoch, wenn Sie mit nothrownew.obj verknüpfen, die Standardeinstellung `operator new` in der C++-Standardbibliothek nicht mehr funktioniert.  
  
 Eine Liste der Bibliotheksdateien, die die C-Laufzeitbibliothek und C++-Standardbibliothek umfassen, finden Sie unter [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  
  
##  <a id="new_operator"> </a> Das new-operator  
 Wenn eine Anweisung ähnlich der folgenden in einem Programm gefunden wird, wird sie in einen Aufruf der Funktion `operator new` übersetzt:  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
Wenn keine Speicherbytes, angefordert wird **new-Operator** gibt einen Zeiger auf ein bestimmtes Objekt (d. h. wiederholte Aufrufe von **new-Operator** geben also unterschiedliche Zeiger zurück). Wenn nicht genügend für die zuordnungsanforderung Arbeitsspeicher **new-Operator** löst eine Std:: bad_alloc-Ausnahme aus, oder gibt **Nullptr** Wenn Sie nicht auslösend verknüpft haben `operator new` unterstützen.  
  
Sie können eine Routine schreiben, die versucht, nur dann Arbeitsspeicher freigeben, und wiederholen die Zuordnung. finden Sie unter [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) für Weitere Informationen. Weitere Details wiederherstellungsschema finden Sie unter der Behandlung von unzureichendem Arbeitsspeicher Abschnitt dieses Themas.  

  
Die beiden Bereiche für `operator new`-Funktionen werden in der folgenden Tabelle beschrieben.  
  
### <a name="scope-for-operator-new-functions"></a>Bereich für "operator new"-Funktionen  
  
|Operator|Bereich|  
|--------------|-----------|  
|**::operator new**|Global|  
|*class-name* **::operator new**|Klasse|  
  
 Das erste Argument für **new-Operator** muss vom Typ **Size_t** (einen Typ in \<stddef.h >), und der Rückgabetyp ist immer **"void" \***  .  
  
 Die globale **new-Operator** Funktion wird aufgerufen, wenn die **neue** Operator wird verwendet, um Objekte des integrierten Typs zuweisen, Objekte des Klassentyps, die keine enthalten benutzerdefinierte **new-Operator** Funktionen und Arrays eines beliebigen Typs. Wenn die **neue** Operator wird verwendet, um Objekte eines Klassentyps zuzuweisen, in denen ein **new-Operator** definiert ist, dieser Klasse **new-Operator** aufgerufen wird.  
  
 Ein **new-Operator** für eine Klasse mit einer statischen Memberfunktion (die daher nicht virtuell sein kann) ist, die die globale ausblendet definierte Funktion **new-Operator** -Funktion für Objekte dieses Klassentyps. Betrachten Sie den Fall, in dem **neue** dient zum Zuordnen und Arbeitsspeicher auf einem angegebenen Wert festgelegt:  
  
```cpp  
// spec1_the_operator_new_function1.cpp  
#include <malloc.h>  
#include <memory.h>  
  
class Blanks  
{  
public:  
    Blanks(){}  
    void *operator new( size_t stAllocateBlock, char chInit );  
};  
void *Blanks::operator new( size_t stAllocateBlock, char chInit )  
{  
    void *pvTemp = malloc( stAllocateBlock );  
    if( pvTemp != 0 )  
        memset( pvTemp, chInit, stAllocateBlock );  
    return pvTemp;  
}  
// For discrete objects of type Blanks, the global operator new function  
// is hidden. Therefore, the following code allocates an object of type  
// Blanks and initializes it to 0xa5  
int main()  
{  
   Blanks *a5 = new(0xa5) Blanks;  
   return a5 != 0;  
}  
```  
  
 Das Argument in Klammern einschließen, um **neue** übergeben `Blanks::operator new` als die `chInit` Argument. Allerdings die globale **new-Operator** Funktion wird ausgeblendet, Code wie der folgende einen Fehler verursacht:  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 In Visual C++ 5.0 und früher verwendeten nichtklassentypen und alle Arrays (unabhängig davon, ob sie von wären **Klasse** Typ) zugeordnet, mit der **neue** -Operator verwendet immer die globale **new-Operator** Funktion.  
  
 Ab Visual C++ 5.0, unterstützt der Compiler memberarray- **neue** und **löschen** Operatoren in einer Klassendeklaration. Zum Beispiel:  
  
```cpp  
// spec1_the_operator_new_function2.cpp  
class MyClass  
{  
public:  
   void * operator new[] (size_t)  
   {  
      return 0;  
   }  
   void   operator delete[] (void*)  
   {  
   }  
};  
  
int main()   
{  
   MyClass *pMyClass = new MyClass[5];  
   delete [] pMyClass;  
}  
```  
  
### <a name="handling-insufficient-memory"></a>Behandeln von ungenügendem Arbeitsspeicher  
 Eine Überprüfung auf fehlerhafte Speicherbelegung kann mit Code wie dem folgenden durchgeführt werden:  
  
```cpp  
// insufficient_memory_conditions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
#define BIG_NUMBER 100000000  
int main() {  
   int *pI = new int[BIG_NUMBER];  
   if( pI == 0x0 ) {  
      cout << "Insufficient memory" << endl;  
      return -1;  
   }  
}  
```  
  
 Es wird eine andere Möglichkeit, Fehler bei speicherbelegungsanforderungen zu behandeln: Schreiben Sie eine benutzerdefinierte wiederherstellungsroutine, um solche Fehler zu behandeln, und registrieren Sie Ihre Funktion durch Aufrufen der [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) Laufzeitfunktion.  
  
##  <a id="delete_operator"> </a> Der Delete-operator  
 Arbeitsspeicher, der dynamisch zugeordnet wird mithilfe der **neue** Operator kann freigegeben werden, mithilfe der **löschen** Operator. Die Delete-Operator Ruft die **Delete-Operator** -Funktion, die Arbeitsspeicher für den verfügbaren Pool wieder frei. Mithilfe der **löschen** Operator auch der Klassendestruktor (sofern vorhanden), die aufgerufen wird.  
  
 Es gibt globale und klassenspezifische **Delete-Operator** Funktionen. Nur ein **Delete-Operator** -Funktion kann für eine angegebene Klasse definiert werden; Wenn definiert, blendet die globale **Delete-Operator** Funktion. Die globale **Delete-Operator** Funktion immer für Arrays jeglichen Typs aufgerufen wird.  
  
 Die globale **Delete-Operator** Funktion. Es gibt zwei Formen der globalen **Delete-Operator** und Klassenmember- **Delete-Operator** Funktionen:  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Nur einer der vorangehenden zwei Formen kann für eine bestimmte Klasse vorhanden sein. Die erste Form akzeptiert ein einzelnes Argument vom Typ **"void" \*** , das einen Zeiger auf das Objekt, das Aufheben der Zuordnung enthält. Die zweite Form – Zuordnung mit Größeninformationen – akzeptiert zwei Argumente: das erste ist ein Zeiger auf den freizugebenden Speicherblock und das zweite ist die Anzahl der freizugebenden Bytes. Ist der Rückgabetyp der beiden Formen `void` (**Delete-Operator** kann keinen Wert zurückgeben).  
  
 Zur Beschleunigung Suche für die richtige Größenkategorie des Objekts, das gelöscht werden, die häufig nicht in der Nähe der Zuordnung selbst gespeichert und wahrscheinlich nicht zwischengespeichert wird ist die zweite Form; die zweite Form ist besonders nützlich, wenn ein **Delete-Operator** Funktion von einer Basisklasse wird verwendet, um ein Objekt einer abgeleiteten Klasse zu löschen.  
  
 Die **Delete-Operator** -Funktion ist statisch und nicht aus diesem Grund virtuell sein. Die `operator delete` Funktion folgt der Zugriffssteuerung wie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).  
  
 Das folgende Beispiel zeigt eine benutzerdefinierte **new-Operator** und **Delete-Operator** Funktionen entwickelt, um speicherbelegungen und Aufhebungen von speicherzuordnungen zu protokollieren:  
  
```cpp  
// spec1_the_operator_delete_function1.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <iostream>  
using namespace std;  
  
int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?  
int cBlocksAllocated = 0;  // Count of blocks allocated.  
  
// User-defined operator new.  
void *operator new( size_t stAllocateBlock ) {  
   static int fInOpNew = 0;   // Guard flag.  
  
   if ( fLogMemory && !fInOpNew ) {  
      fInOpNew = 1;  
      clog << "Memory block " << ++cBlocksAllocated  
          << " allocated for " << stAllocateBlock  
          << " bytes\n";  
      fInOpNew = 0;  
   }  
   return malloc( stAllocateBlock );  
}  
  
// User-defined operator delete.  
void operator delete( void *pvMem ) {  
   static int fInOpDelete = 0;   // Guard flag.  
   if ( fLogMemory && !fInOpDelete ) {  
      fInOpDelete = 1;  
      clog << "Memory block " << cBlocksAllocated--  
          << " deallocated\n";  
      fInOpDelete = 0;  
   }  
  
   free( pvMem );  
}  
  
int main( int argc, char *argv[] ) {  
   fLogMemory = 1;   // Turn logging on  
   if( argc > 1 )  
      for( int i = 0; i < atoi( argv[1] ); ++i ) {  
         char *pMem = new char[10];  
         delete[] pMem;  
      }  
   fLogMemory = 0;  // Turn logging off.  
   return cBlocksAllocated;  
}  
```  
  
 Mit dem vorangehenden Code kann "Arbeitsspeicherverlust" erkannt werden, also Arbeitsspeicher, der im freien Speicher zugeordnet, jedoch nicht freigegeben wurde. Diese Erkennung, die die globale auszuführenden **neue** und **löschen** Operatoren zum Belegen und Freigeben des Arbeitsspeichers Anzahl neu definiert.  
  
 Ab Visual C++ 5.0, unterstützt der Compiler memberarray- **neue** und **löschen** Operatoren in einer Klassendeklaration. Zum Beispiel:  
  
```cpp  
// spec1_the_operator_delete_function2.cpp  
// compile with: /c  
class X  {  
public:  
   void * operator new[] (size_t) {  
      return 0;  
   }  
   void operator delete[] (void*) {}  
};  
  
void f() {  
   X *pX = new X[5];  
   delete [] pX;  
}  
```  

