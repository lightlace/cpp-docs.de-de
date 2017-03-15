---
title: "Operatoren &quot;new&quot; und &quot;delete&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "delete_cpp"
  - "new_cpp"
  - "new"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete-Schlüsselwort [C++], Syntax"
  - "new-Schlüsselwort [C++], Dynamische Zuordnung von Objekten"
  - "nothrownew.obj"
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Operatoren &quot;new&quot; und &quot;delete&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ unterstützt die dynamische Zuordnung und Freigabe von Objekten mit den Operatoren [new](../cpp/new-operator-cpp.md) und [delete](../cpp/delete-operator-cpp.md).  Diese Operatoren belegen Speicher für Objekte aus einem Pool, der als freier Speicher bezeichnet wird.  Der `new`\-Operator ruft die Spezialfunktion [operator new](../misc/operator-new-function.md) auf, und der `delete`\-Operator ruft die Spezialfunktion [operator delete](../misc/operator-delete-function.md) auf.  
  
 In [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] .NET 2002 unterstützt die `new`\-Funktion in der C\+\+\-Standardbibliothek das Verhalten, das im C\+\+\-Standard angegeben wird, nämlich eine std::bad\_alloc\-Ausnahme auszulösen, wenn die Speicherbelegung fehlschlägt.  
  
 Auch die `new`\-Funktion der C\-Laufzeitbibliothek löst eine std::bad\_alloc\-Ausnahme aus, wenn die Speicherbelegung fehlschlägt.  
  
 Wenn Sie die nicht auslösende Version von `new` für die C\-Laufzeitbibliothek verwenden möchten, verknüpfen Sie das Programm mit nothrownew.obj.  Wenn Sie jedoch mit nothrownew.obj verknüpfen, funktioniert `new` in der C\+\+\-Standardbibliothek nicht mehr.  
  
 Eine Liste der Bibliotheksdateien, die die C\-Laufzeitbibliothek und die C\+\+\-Standardbibliothek enthalten, finden Sie unter [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).  
  
## Der new\-Operator  
 Wenn eine Anweisung ähnlich der folgenden in einem Programm gefunden wird, wird sie in einen Aufruf der Funktion `operator new` übersetzt:  
  
```  
char *pch = new char[BUFFER_SIZE];  
```  
  
 Wenn keine Speicherbytes angefordert werden, gibt **operator new**einen Zeiger auf ein bestimmtes Objekt zurück \(wiederholte Aufrufe von **operator new** geben also unterschiedliche Zeiger zurück\).  Wenn für die Belegungsanforderung kein ausreichender Arbeitsspeicher zur Verfügung steht, gibt **operator new**den Wert **NULL** zurück oder löst eine Ausnahme aus \(Weitere Informationen finden Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md)\).  
  
 Sie können eine Routine schreiben, die versucht, Speicherplatz freizugeben, und die Speicherbelegung wiederholen. Weitere Informationen finden Sie unter [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md).  Weitere Informationen zum Wiederherstellungsschema finden Sie im folgenden Thema [Unzureichende Arbeitsspeicher\-Zustände behandeln](../misc/handling-insufficient-memory-conditions.md).  
  
 Die beiden Bereiche für `operator new`\-Funktionen werden in der folgenden Tabelle beschrieben.  
  
### Bereich für "operator new"\-Funktionen  
  
|Operator|Bereich|  
|--------------|-------------|  
|**::operator new**|Global|  
|*class\-name* **::operator new**|Klasse|  
  
 Das erste Argument für **operator new** muss vom Typ **size\_t** sein \(ein Typ, der in STDDEF.H definiert ist\), und der Rückgabetyp ist immer **void \***.  
  
 Die globale Funktion **operator new** wird aufgerufen, wenn der Operator **new** verwendet wird, um Objekte des integrierten Typs, Objekte des Klassentyps, die keine benutzerdefinierten **operator new**\-Funktionen enthalten, sowie Arrays jeglichen Typs zuzuordnen.  Wenn der **new**\-Operator verwendet wird, um Objekte eines Klassentyps zuzuweisen, in dem **operator new**definiert ist, wird **operator new** dieser Klasse aufgerufen.  
  
 Eine **operator new**\-Funktion, die für eine Klasse definiert wird, ist eine statischen Memberfunktion \(die daher nicht virtuell sein kann\), die die globale **operator new**\-Funktion für Objekte dieses Klassentyps ausblendet.  Betrachten Sie den Fall, in dem **new** verwendet wird, um Arbeitsspeicher zuzuweisen und auf einen angegebenen Wert festzulegen:  
  
```  
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
  
 Das Argument, das in Klammern für **new** bereitgestellt wird, wird an `Blanks::operator new` als `chInit`\-Argument übergeben.  Allerdings wird die globale **operator new**\-Funktion ausgeblendet und bewirkt, dass Code wie der Folgende einen Fehler generiert:  
  
```  
Blanks *SomeBlanks = new Blanks;  
```  
  
 In Visual C\+\+ 5.0 und früher verwendeten Nichtklassentypen und alle Arrays \(unabhängig davon, ob sie vom **class**\-Typ waren\), die mithilfe des **new**\-Operators zugewiesen wurden, immer die globale **operator new**\-Funktion.  
  
 Ab Visual C\+\+ 5.0, unterstützt der Compiler Memberarray\-**new**\- und **delete**\-Operatoren in einer Klassendeklaration.  Zum Beispiel:  
  
```  
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
  
### Behandeln von ungenügendem Arbeitsspeicher  
 Eine Überprüfung auf fehlerhafte Speicherbelegung kann mit Code wie dem folgenden durchgeführt werden:  
  
```  
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
  
 Es gibt eine andere Möglichkeit, um Fehler bei Speicherbelegungsanforderungen zu behandeln: Schreiben Sie eine benutzerdefinierte Wiederherstellungsroutine, um einen solchen Fehler zu behandeln, und registrieren Sie Ihre Funktion anschließend, indem Sie die Laufzeitfunktion [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md) aufrufen.  
  
## Der delete\-Operator  
 Arbeitsspeicher, der mithilfe des **new**\-Operators dynamisch zugeordnet wird, kann mithilfe des **delete**\-Operators freigegeben werden.  Der delete\-Operator ruft die Funktion **Operator delete** auf, die Speicherplatz für den verfügbaren Pool frei macht.  Durch die Verwendung des **delete**\-Operators wird auch der Klassendestruktor \(falls vorhanden\) aufgerufen.  
  
 Es gibt globale und klassenspezifische **operator delete**\-Funktionen.  Es kann nur eine **operator delete**\-Funktion für eine angegebene Klasse definiert werden. Sofern definiert, blendet sie die globale **operator delete**\-Funktion aus.  Die globale **operator delete**\-Funktion wird immer für Arrays jeglichen Typs aufgerufen.  
  
 Sofern deklariert, verwendet die globale **operator delete**\-Funktion ein einzelnes Argument vom Typ **void \***, das einen Zeiger auf das Objekt enthält, dessen Zuordnung aufgehoben werden soll.  Der Rückgabetyp ist `void` \(**Operator delete** kann keinen Wert zurückgeben\).  Es gibt zwei Formen für **operator delete**\-Funktionen von Klassenmembern:  
  
```  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Nur eine der vorherigen beiden Varianten kann für eine angegebene Klasse vorhanden sein.  Die erste Form funktioniert wie beschrieben für globale `operator delete`.  Die zweite Form verwendet zwei Argumente, das erste Argument ist ein Zeiger auf den freizugebenden Speicherblock und das zweite Argument ist die Anzahl der freizugebenden Bytes.  Die zweite Form ist besonders nützlich, wenn eine **Operator delete**\-Funktion aus einer Basisklasse verwendet wird, um ein Objekt einer abgeleiteten Klasse zu löschen.  
  
 Die **Operator delete**\-Funktion ist statisch und kann daher nicht virtuell sein.  Die `operator delete`\-Funktion folgt der Zugriffssteuerung wie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) beschrieben.  
  
 Das folgende Beispiel zeigt die benutzerdefinierten Funktionen **operator new** und **operator delete**, die dazu dienen, Speicherzuordnungen und Aufhebungen von Speicherzuordnungen zu protokollieren:  
  
```  
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
  
 Mit dem vorangehenden Code kann "Arbeitsspeicherverlust" erkannt werden, also Arbeitsspeicher, der im freien Speicher zugeordnet, jedoch nicht freigegeben wurde.  Um diese Erkennung auszuführen, werden die globalen Operatoren **new** und **delete** neu definiert, um die Speicherbelegung und die Freigabe der Speicherbelegung zu zählen.  
  
 Ab Visual C\+\+ 5.0, unterstützt der Compiler Memberarray\-**new**\- und **delete**\-Operatoren in einer Klassendeklaration.  Zum Beispiel:  
  
```  
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
  
## Siehe auch  
 [Spezielle Memberfunktionen](../misc/special-member-functions-cpp.md)