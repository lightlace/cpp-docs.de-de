---
title: Operatoren "new" und "delete"
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 1ac6282ecbf45f22e7dd66b94f8bccdbc4e505ce
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345894"
---
# <a name="new-and-delete-operators"></a>Operatoren "new" und "delete"

C++ unterstützt die dynamische Zuordnung und Freigabe von Objekten mit den [neue](../cpp/new-operator-cpp.md) und [löschen](../cpp/delete-operator-cpp.md) Operatoren. Diese Operatoren belegen Speicher für Objekte aus einem Pool, der als freier Speicher bezeichnet wird. Die **neue** Operator Ruft die Spezialfunktion [new-Operator](../cpp/new-operator-cpp.md), und die **löschen** Operator Ruft die Spezialfunktion [Delete-Operator](../cpp/delete-operator-cpp.md).

Die **neue** Funktion in der C++ Standardbibliothek unterstützt das Verhalten der C++ Standard besteht darin, eine Std:: bad_alloc-Ausnahme auslösen, wenn die speicherbelegung fehlschlägt. Falls Sie weiterhin die nicht auslösende Version von benötigen **neue**, Ihr Programm mit nothrownew.obj verknüpfen. Aber wenn Sie mit nothrownew.obj verknüpfen, die Standardeinstellung **new-Operator** in der C++-Standardbibliothek nicht mehr funktioniert.

Eine Liste der Bibliotheksdateien, die die C-Laufzeitbibliothek und C++-Standardbibliothek enthalten, finden Sie unter [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).

##  <a id="new_operator"> </a> Das new-operator

Wenn eine Anweisung ähnlich der folgenden in einem Programm gefunden wird, ist er in einen Aufruf der Funktion übersetzt **new-Operator**:

```cpp
char *pch = new char[BUFFER_SIZE];
```

Wenn keine Speicherbytes, die Anforderung ist **new-Operator** gibt einen Zeiger auf ein bestimmtes Objekt (d. h. wiederholte Aufrufe von **new-Operator** liefern also unterschiedliche Zeiger). Es ist nicht genügend Arbeitsspeicher für die zuordnungsanforderung **new-Operator** löst eine Std:: bad_alloc-Ausnahme aus, oder gibt **"nullptr"** bei Links in nicht auslösend **new-Operator** unterstützen.

Sie können eine Routine schreiben, die versucht, den Speicher frei, und wiederholen die Zuordnung. finden Sie unter [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) für Weitere Informationen. Weitere Informationen wiederherstellungsschema finden Sie im Abschnitt behandeln nicht genügend Arbeitsspeicher in diesem Thema.

Die beiden Bereiche für **new-Operator** Funktionen werden in der folgenden Tabelle beschrieben.

### <a name="scope-for-operator-new-functions"></a>Bereich für "operator new"-Funktionen

|Operator|Bereich|
|--------------|-----------|
|**:: new-Operator**|Global|
|*Klassennamen* **:: new-Operator**|Klasse|

Das erste Argument für **new-Operator** muss vom Typ `size_t` (in definierten Typs \<stddef.h >), und der Rückgabetyp ist immer **"void"** <strong>\*</strong>.

Die globale **new-Operator** Funktion wird aufgerufen, wenn die **neue** Operator wird verwendet, um Objekte von integrierten Typen zuordnen, Objekte des Klassentyps, die keine enthalten benutzerdefinierte **new-Operator** Funktionen sowie Arrays jeglichen Typs. Wenn die **neue** Operator wird verwendet, um Objekte eines Klassentyps zuzuweisen, in denen ein **new-Operator** definiert ist, dieser Klasse **new-Operator** aufgerufen wird.

Ein **new-Operator** Funktion, die für eine Klasse mit einer statischen Memberfunktion (die daher nicht virtuell sein kann) ist, die die globale verbirgt definiert **new-Operator** -Funktion für Objekte dieses Klassentyps. Betrachten Sie den Fall, in denen **neue** dient zum Zuordnen und Speicher auf einem angegebenen Wert festgelegt:

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

Das Argument in Klammern angegeben **neue** übergeben wird, um `Blanks::operator new` als die `chInit` Argument. Allerdings die globale **new-Operator** Funktion wird ausgeblendet, wodurch Code wie der folgende Fehler generiert:

```cpp
Blanks *SomeBlanks = new Blanks;
```

In Visual C++ 5.0 und früher verwendeten nichtklassentypen und alle Arrays (unabhängig davon, ob sie von Waren **Klasse** Typ) zugeordnet, mit der **neue** -Operator verwendet immer die globale **new-Operator** Funktion.

Ab Visual C++ 5.0 unterstützt der Compiler memberarray **neue** und **löschen** Operatoren in einer Klassendeklaration. Zum Beispiel:

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

Es gibt eine andere Möglichkeit, Fehler bei speicherbelegungsanforderungen zu behandeln: Schreiben Sie eine benutzerdefinierte wiederherstellungsroutine, um solche Fehler zu behandeln, und registrieren Sie Ihre Funktion durch Aufrufen der [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) Run-Time-Funktion.

##  <a id="delete_operator"> </a> Der Delete-operator

Arbeitsspeicher, die dynamisch zugewiesen wird, mit der **neue** Operator kann freigegeben werden, mithilfe der **löschen** Operator. Die Delete-Operator Ruft die **Delete-Operator** -Funktion, die Speicherplatz für den verfügbaren Pool frei macht. Mithilfe der **löschen** auch bewirkt, dass den Destruktor einer Klasse (sofern vorhanden) aufgerufen werden.

Es gibt globale und klassenspezifische **Delete-Operator** Funktionen. Nur ein **Delete-Operator** -Funktion für eine angegebene Klasse definiert werden kann; sofern definiert, blendet die globale **Delete-Operator** Funktion. Die globale **Delete-Operator** Funktion wird immer für Arrays jeglichen Typs aufgerufen.

Die globale **Delete-Operator** Funktion. Es gibt zwei Formen für die globale **Delete-Operator** und Klassenmember- **Delete-Operator** Funktionen:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Nur eine der beiden oben beschriebenen Formen kann für eine bestimmte Klasse vorhanden sein. Die erste Form akzeptiert ein einzelnes Argument vom Typ `void *`, das einen Zeiger auf das Objekt beim Aufheben der Zuordnung enthält. Die zweite Form – Größeninformationen – akzeptiert zwei Argumente: das erste Argument ist ein Zeiger auf den Speicherblock beim Aufheben der Zuordnung und die zweite ist die Anzahl der freizugebenden Bytes. Der Rückgabetyp der beiden Formen **"void"** (**Delete-Operator** kann keinen Wert zurückgeben).

Um eine schnellere suchen, die für die Kategorie der richtigen Größe des Objekts, das gelöscht werden, der oft nicht in der Nähe der Zuordnung selbst gespeichert und wahrscheinlich nicht zwischengespeichert, die zweite Form ist; die zweite Form ist besonders nützlich, wenn ein **Delete-Operator** Funktion von einer Basisklasse wird verwendet, um ein Objekt einer abgeleiteten Klasse zu löschen.

Die **Delete-Operator** -Funktion ist statisch und nicht aus diesem Grund virtuell sein. Die **Delete-Operator** Funktion folgt der Zugriffssteuerung wie beschrieben in [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).

Das folgende Beispiel zeigt eine benutzerdefinierte **new-Operator** und **Delete-Operator** Funktionen, die dazu dienen, speicherzuordnungen und Aufhebungen von speicherzuordnungen zu protokollieren:

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

Mit dem vorangehenden Code kann "Arbeitsspeicherverlust" erkannt werden, also Arbeitsspeicher, der im freien Speicher zugeordnet, jedoch nicht freigegeben wurde. Zum Ausführen dieser Erkennung wird die globale **neue** und **löschen** Operatoren zum Belegen und Freigeben des Arbeitsspeichers Anzahl neu definiert.

Ab Visual C++ 5.0 unterstützt der Compiler memberarray **neue** und **löschen** Operatoren in einer Klassendeklaration. Zum Beispiel:

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