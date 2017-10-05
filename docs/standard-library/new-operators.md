---
title: '&lt;new&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
caps.latest.revision: 8
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 32707847948c32f671e7ebd7def23165b59a63a8
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltnewgt-operators"></a>&lt;new&gt;-Operatoren
||||  
|-|-|-|  
|[operator delete](#op_delete)|[operator delete[]](#op_delete_arr)|[operator new](#op_new)|  
|[operator new[]](#op_new_arr)|  
  
##  <a name="op_delete"></a> operator delete  
 Die Funktion, die durch einen Löschausdruck aufgerufen wird, um Speicher für einzelne Objekte freizugeben.  
  
```
void operator delete(void* ptr) throw();

void operator delete(void *,
    void*) throw();

void operator delete(void* ptr,
    const std::nothrow_t&) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ptr`  
 Der Zeiger, dessen Wert durch den Löschvorgang als ungültig gerendert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion wird durch einen Löschausdruck aufgerufen, um den Werts von `ptr` als ungültig zu rendern. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Als erforderliches Verhalten soll ein Wert von `ptr` akzeptiert werden, der gleich 0 (null) ist oder durch einen früheren Aufruf von [operator new](../standard-library/new-operators.md#op_new)( **size_t**) zurückgegeben wurde.  
  
 Als Standardverhalten für einen null-Wert von `ptr` geschieht nichts. Jeder andere Wert von `ptr` muss ein Wert sein, der zuvor durch einen Aufruf zurückgegeben wurde (siehe oben). Als Standardverhalten für einen Wert ungleich 0 (null) von `ptr` soll der durch den früheren Aufruf belegte Speicherplatz freigegeben werden. Es wird nicht angegeben, unter welchen Umständen Speicherplatz dieser Art teilweise oder vollständig durch einen nachfolgenden Aufruf von `operator new`( **size_t**) bzw. einem beliebigen `calloc`( **size_t**), `malloc`( **size_t**) oder `realloc`( **void\***, **size_t**) zugeordnet wird.  
  
 Die zweite Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden new-Ausdruck der Form **new**( **std:: size_t**) aufgerufen. Dabei wird keine Aktion ausgeführt.  
  
 Die dritte Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden new-Ausdruck der Form **new**( **std::size_t**, **conststd::nothrow_t&**) aufgerufen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Als erforderliches Verhalten soll ein Wert von `ptr` akzeptiert werden, der gleich 0 (null) ist oder durch einen früheren Aufruf von `operator new`( **size_t**). zurückgegeben wurde. Standardmäßig wird **delete**( `ptr`). zurückgegeben.  
  
### <a name="example"></a>Beispiel  
  Unter [operator new](../standard-library/new-operators.md#op_new) finden Sie ein Beispiel mit `operator delete`.  
  
##  <a name="op_delete_arr"></a> operator delete[]  
 Die Funktion, die durch einen Löschausdruck (delete-Ausdruck) aufgerufen wird, um Speicher für ein Array von Objekten freizugeben.  
  
```
void operator delete[](void* ptr) throw();

void operator delete[](void *,
    void*) throw();

void operator delete[](void* ptr,
    const std::nothrow_t&) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ptr`  
 Der Zeiger, dessen Wert durch den Löschvorgang als ungültig gerendert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion wird durch einen `delete[]`-Ausdruck aufgerufen, um den Wert von `ptr` als ungültig zu rendern. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Als erforderliches Verhalten soll ein Wert von `ptr` akzeptiert werden, der gleich 0 (null) ist oder durch einen früheren Aufruf von [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)( **size_t**) zurückgegeben wurde. Als Standardverhalten für einen null-Wert von `ptr` geschieht nichts. Jeder andere Wert von `ptr` muss ein Wert sein, der zuvor durch einen Aufruf zurückgegeben wurde (siehe oben). Als Standardverhalten für einen Wert ungleich 0 (null) von `ptr` soll der durch den früheren Aufruf belegte Speicherplatz freigegeben werden. Es wird nicht angegeben, unter welchen Umständen Speicherplatz dieser Art teilweise oder vollständig durch einen nachfolgenden Aufruf von [operator new](../standard-library/new-operators.md#op_new)( **size_t**) bzw. einem beliebigen `calloc`( **size_t**), `malloc`( **size_t**), or `realloc`( **void\***, **size_t**). zugeordnet wird.  
  
 Die zweite Funktion wird durch einen Placement-`delete[]`-Ausdruck für einen entsprechenden `new[]`-Ausdruck der Form `new[]`( **std::size_t**) aufgerufen. Dabei wird keine Aktion ausgeführt.  
  
 Die dritte Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden `new[]`-Ausdruck der Form `new[]`( **std::size_t**, **const std::nothrow_t&**) aufgerufen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Als erforderliches Verhalten soll ein Wert von `ptr` akzeptiert werden, der gleich 0 (null) ist oder durch einen früheren Aufruf von Operator `new[]`( **size_t**) zurückgegeben wurde. Standardmäßig wird `delete[]`( `ptr`) ausgewertet.  
  
### <a name="example"></a>Beispiel  
  Unter [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) finden Sie Beispiele für die Verwendung von `operator delete[]`.  
  
##  <a name="op_new"></a> operator new  
 Die Funktion, die durch einen new-Ausdruck aufgerufen wird, um Speicher für einzelne Objekte zu belegen.  
  
```
void* operator new(std::size_t count) throw(bad_alloc);

void* operator new(std::size_t count,
    const std::nothrow_t&) throw();

void* operator new(std::size_t count,
    void* ptr) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `count`  
 Der zu belegende Speicherplatz in Bytes.  
  
 `ptr`  
 Der Zeiger, der zurückgegeben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Entweder ein Zeiger auf die niedrigste Byteadresse des neu belegten Speichers oder `ptr.`.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion wird durch einen new-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt.  
  
 Als erforderliches Verhalten wird ein nicht-NULL-Zeiger nur dann zurückgegeben, wenn Speicherplatz wie gewünscht belegt werden kann. Alle Zuordnungen dieser Art geben einen Zeiger auf Speicherplatz aus, der nicht mit belegtem Speicherplatz zusammenhängt. Reihenfolge und Kontinuität von durch aufeinanderfolgende Aufrufe belegtem Speicherplatz werden nicht angegeben. Auch der anfänglich gespeicherte Wert wird nicht angegeben. Der zurückgegebene Zeiger verweist auf den Anfang (niedrigste Byteadresse) des belegten Speicherplatzes. Wenn die Anzahl 0 (null) ist, entspricht der zurückgegebene Wert keinem der anderen Werte, die von der Funktion zurückgegeben wurden.  
  
 Standardmäßig wird eine Schleife ausgeführt. Innerhalb der Schleife versucht die Funktion zuerst den angeforderten Speicherplatz zu belegen. Es wird nicht angegeben, ob der Versuch einen Aufruf von `malloc`( **size_t**) umfasst. Wenn der Versuch erfolgreich ist, gibt die Funktion einen Zeiger auf den belegten Speicherplatz zurück. Ansonsten gibt die Funktion den festgelegten [new handler](../standard-library/new-typedefs.md#new_handler) zurück. Führt die aufgerufene Funktion eine Rückgabe aus, wird die Schleife wiederholt. Die Schleife wird beendet, wenn ein Versuch zur Belegung des angeforderten Speichers erfolgreich ist oder eine aufgerufene Funktion keine Rückgabe ausführt.  
  
 Als erforderliches Verhalten für einen neuen Handler ist eine der folgenden Operationen auszuführen:  
  
-   Stellt zusätzlichen Speicherplatz für die Zuordnung bereit und springt anschließend zurück.  
  
-   Ruft entweder **abort** oder **exit**( `int`) auf.  
  
-   Löst ein Objekt des Typs **bad_alloc** aus.  
  
 Standardmäßig wird für einen [new handler](../standard-library/new-typedefs.md#new_handler) ein Objekt des Typs `bad_alloc` ausgelöst. Ein NULL-Zeiger legt den neuen Standard-Handler fest.  
  
 Reihenfolge und Kontinuität von durch aufeinanderfolgende Aufrufe von `operator new`( **size_t**) belegtem Speicherplatz werden nicht angegeben. Dies gilt auch für die dort gespeicherten Anfangswerte.  
  
 Die zweite Funktion wird durch einen Placement-new-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt.  
  
 Wird die Funktion erfolgreich ausgeführt, wird standardmäßig `operator new`( `count`) zurückgegeben. Ansonsten gibt sie einen NULL-Zeiger zurück.  
  
 Die dritte Funktion wird durch einen Placement-**new**-Ausdruck der Form **new** ( *args*) T aufgerufen. In diesem Fall besteht *args* aus einem einzelnen Objektzeiger. Dies kann sich beim Erstellen eines Objekts an einer bekannten Adresse als nützlich erweisen. Die Funktion gibt *ptr* zurück.  
  
 Rufen Sie [operator delete](../standard-library/new-operators.md#op_delete) auf, um durch `operator new` belegten Speicherplatz freizugeben.  
  
 Informationen zum Auslöseverhalten von „new“ finden Sie unter [new-Operator und delete-Operator](../cpp/new-and-delete-operators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// new_op_new.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
  
class MyClass   
{  
public:   
   MyClass( )  
   {  
      cout << "Construction MyClass." << this << endl;  
   };  
  
   ~MyClass( )  
   {  
      imember = 0; cout << "Destructing MyClass." << this << endl;  
   };  
   int imember;  
};  
  
int main( )   
{  
   // The first form of new delete  
   MyClass* fPtr = new MyClass;  
   delete fPtr;  
  
   // The second form of new delete  
   MyClass* fPtr2 = new( nothrow ) MyClass;  
   delete fPtr2;  
  
   // The third form of new delete  
   char x[sizeof( MyClass )];  
   MyClass* fPtr3 = new( &x[0] ) MyClass;  
   fPtr3 -> ~MyClass();  
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;  
}  
```  
  
##  <a name="op_new_arr"></a> operator new[]  
 Die Zuordnungsfunktion, die durch einen new-Ausdruck aufgerufen wird, um Speicherplatz für ein Array von Objekten zu belegen.  
  
```
void* operator new[](std::size_t count) throw(std::bad_alloc);

void* operator new[](std::size_t count,
    const std::nothrow_t&) throw();

void* operator new[](std::size_t count,
    void* ptr) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `count`  
 Der Speicherplatz in Bytes, der für ein Array-Objekt belegt werden soll.  
  
 `ptr`  
 Der Zeiger, der zurückgegeben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Entweder ein Zeiger auf die niedrigste Byteadresse des neu belegten Speichers oder `ptr.`.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Funktion wird durch einen `new[]`-Ausdruck aufgerufen, um `count`-Bytes im Speicher zu belegen, die genau auf alle Array-Objekte ausgerichtet sind, die höchstens diese Größe aufweisen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das erforderliche Verhalten entspricht dem Verhalten für [operator new](../standard-library/new-operators.md#op_new)( **size_t**). Standardmäßig wird `operator new`( `count`) zurückgegeben.  
  
 Die zweite Funktion wird durch einen Placement-`new[]`-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Wird diese Funktion erfolgreich ausgeführt, so wird standardmäßig **operatornew**( `count`) zurückgegeben. Ansonsten gibt sie einen NULL-Zeiger zurück.  
  
 Die dritte Funktion wird durch einen Placement-`new[]`-Ausdruck der Form **new** ( *args*) **T**[ **N**] aufgerufen. In diesem Fall besteht *args* aus einem einzelnen Objektzeiger. Die Funktion gibt `ptr` zurück.  
  
 Rufen Sie [operator delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr) auf, um durch `operator new[]` belegten Speicherplatz freizugeben.  
  
 Informationen zum Auslöseverhalten von „new“ finden Sie unter [new-Operator und delete-Operator](../cpp/new-and-delete-operators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// new_op_alloc.cpp  
// compile with: /EHsc  
#include <new>  
#include <iostream>  
  
using namespace std;  
  
class MyClass {  
public:  
   MyClass() {  
      cout << "Construction MyClass." << this << endl;  
   };  
  
   ~MyClass() {  
      imember = 0; cout << "Destructing MyClass." << this << endl;  
      };  
   int imember;  
};  
  
int main() {  
   // The first form of new delete  
   MyClass* fPtr = new MyClass[2];  
   delete[ ] fPtr;  
  
   // The second form of new delete  
   char x[2 * sizeof( MyClass ) + sizeof(int)];  
  
   MyClass* fPtr2 = new( &x[0] ) MyClass[2];  
   fPtr2[1].~MyClass();  
   fPtr2[0].~MyClass();  
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;  
  
   // The third form of new delete  
   MyClass* fPtr3 = new( nothrow ) MyClass[2];  
   delete[ ] fPtr3;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<new>](../standard-library/new.md)




