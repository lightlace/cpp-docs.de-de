---
title: '&lt;new&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
ms.openlocfilehash: 87f7b6cfd6a06ab03b27ebe6aa4dd41b0b900673
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570533"
---
# <a name="ltnewgt-operators"></a>&lt;new&gt;-Operatoren

||||
|-|-|-|
|[operator delete](#op_delete)|[operator delete[]](#op_delete_arr)|[operator new](#op_new)|
|[operator new[]](#op_new_arr)|

## <a name="op_delete"></a> operator delete

Die Funktion, die durch einen Löschausdruck aufgerufen wird, um Speicher für einzelne Objekte freizugeben.

```cpp
void operator delete(void* ptr) throw();

void operator delete(void *,
    void*) throw();

void operator delete(void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Der Zeiger, dessen Wert durch den Löschvorgang als ungültig gerendert werden soll.

### <a name="remarks"></a>Hinweise

Die erste Funktion wird aufgerufen, durch einen Löschausdruck zum Rendern des Werts der *Ptr* ungültig. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das erforderliche Verhalten ist, akzeptieren den Wert *Ptr* , Null, oder die durch einen früheren Aufruf zurückgegeben wurde [new-Operator](../standard-library/new-operators.md#op_new)(**"size_t"**).

Das Standardverhalten für einen null-Wert des *Ptr* geschieht nichts. Jeder andere Wert von *Ptr* muss ein Wert, der zuvor durch einen Aufruf zurückgegeben wie zuvor beschrieben sein. Das Standardverhalten für diese einen Wert ungleich null der *Ptr* Freigebens von den früheren Aufruf zugeordnet ist. Es wird nicht angegeben, unter welchen Umständen Speicherplatz dieser Art ganz oder teilweise, durch einen nachfolgenden Aufruf von zugeordnet ist `operator new`(**"size_t"**), oder einem beliebigen `calloc`( **"size_t"**), `malloc`( **"size_t"**), oder `realloc`( **"void"**<strong>\*</strong>, **"size_t"**).

Die zweite Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden new-Ausdruck der Form **new**( **std:: size_t**) aufgerufen. Dabei wird keine Aktion ausgeführt.

Die dritte Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden new-Ausdruck der Form **new**( **std::size_t**, **conststd::nothrow_t&**) aufgerufen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Als erforderliches Verhalten soll ein Wert von `ptr` akzeptiert werden, der gleich 0 (null) ist oder durch einen früheren Aufruf von `operator new`( **size_t**). zurückgegeben wurde. Das Standardverhalten ist das bewerten **löschen**(`ptr`).

### <a name="example"></a>Beispiel

Finden Sie unter [new-Operator](../standard-library/new-operators.md#op_new) für ein Beispiel mit **Delete-Operator**.

## <a name="op_delete_arr"></a> operator delete[]

Die Funktion, die durch einen Löschausdruck (delete-Ausdruck) aufgerufen wird, um Speicher für ein Array von Objekten freizugeben.

```cpp
void operator delete[](void* ptr) throw();

void operator delete[](void *,
    void*) throw();

void operator delete[](void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Der Zeiger, dessen Wert durch den Löschvorgang als ungültig gerendert werden soll.

### <a name="remarks"></a>Hinweise

Die erste Funktion wird aufgerufen, indem ein `delete[]` Ausdruck zum Rendern des Werts der *Ptr* ungültig. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das erforderliche Verhalten ist, akzeptieren den Wert *Ptr* , Null, oder die durch einen früheren Aufruf zurückgegeben wurde [new-Operator&#91;&#93;](../standard-library/new-operators.md#op_new_arr)(**"size_t"**). Das Standardverhalten für einen null-Wert des *Ptr* geschieht nichts. Jeder andere Wert von *Ptr* muss ein Wert, der zuvor durch einen Aufruf zurückgegeben wie zuvor beschrieben sein. Das Standardverhalten für diese einen nicht-Null-Wert, der *Ptr* Freigebens von den früheren Aufruf zugeordnet ist. Es wird nicht angegeben, unter welchen Umständen Speicherplatz dieser Art ganz oder teilweise, durch einen nachfolgenden Aufruf von zugeordnet ist [new-Operator](../standard-library/new-operators.md#op_new)(**"size_t"**), oder einem beliebigen `calloc`(**"size_t"**), `malloc`(**"size_t"**), oder `realloc`( **"void"**<strong>\*</strong>, **"size_t"**) .

Die zweite Funktion wird aufgerufen, durch einen Placement- `delete[]` Ausdruck entspricht einer `new[]` Ausdruck der Form `new[]`(**Std:: size_t**). Dabei wird keine Aktion ausgeführt.

Die dritte Funktion wird durch einen Placement-delete-Ausdruck für einen entsprechenden `new[]`-Ausdruck der Form `new[]`( **std::size_t**, **const std::nothrow_t&**) aufgerufen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das erforderliche Verhalten ist, akzeptieren den Wert *Ptr* , Null, oder die durch einen früheren Aufruf von Operator zurückgegeben wurde `new[]`(**"size_t"**). Standardmäßig wird `delete[]`( `ptr`) ausgewertet.

### <a name="example"></a>Beispiel

Unter [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) finden Sie Beispiele für die Verwendung von `operator delete[]`.

## <a name="op_new"></a> operator new

Die Funktion, die durch einen new-Ausdruck aufgerufen wird, um Speicher für einzelne Objekte zu belegen.

```cpp
void* operator new(std::size_t count) throw(bad_alloc);

void* operator new(std::size_t count,
    const std::nothrow_t&) throw();

void* operator new(std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parameter

*count*<br/>
Der zu belegende Speicherplatz in Bytes.

*ptr*<br/>
Der Zeiger, der zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Entweder ein Zeiger auf die niedrigste Byteadresse des neu belegten Speichers Oder *Ptr*.

### <a name="remarks"></a>Hinweise

Die erste Funktion wird durch einen new-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt.

Als erforderliches Verhalten wird ein nicht-NULL-Zeiger nur dann zurückgegeben, wenn Speicherplatz wie gewünscht belegt werden kann. Alle Zuordnungen dieser Art geben einen Zeiger auf Speicherplatz aus, der nicht mit belegtem Speicherplatz zusammenhängt. Reihenfolge und Kontinuität von durch aufeinanderfolgende Aufrufe belegtem Speicherplatz werden nicht angegeben. Auch der anfänglich gespeicherte Wert wird nicht angegeben. Der zurückgegebene Zeiger verweist auf den Anfang (niedrigste Byteadresse) des belegten Speicherplatzes. Wenn die Anzahl 0 (null) ist, entspricht der zurückgegebene Wert keinem der anderen Werte, die von der Funktion zurückgegeben wurden.

Standardmäßig wird eine Schleife ausgeführt. Innerhalb der Schleife versucht die Funktion zuerst den angeforderten Speicherplatz zu belegen. Es wird nicht angegeben, ob der Versuch einen Aufruf von `malloc`( **size_t**) umfasst. Wenn der Versuch erfolgreich ist, gibt die Funktion einen Zeiger auf den belegten Speicherplatz zurück. Ansonsten gibt die Funktion den festgelegten [new handler](../standard-library/new-typedefs.md#new_handler) zurück. Führt die aufgerufene Funktion eine Rückgabe aus, wird die Schleife wiederholt. Die Schleife wird beendet, wenn ein Versuch zur Belegung des angeforderten Speichers erfolgreich ist oder eine aufgerufene Funktion keine Rückgabe ausführt.

Als erforderliches Verhalten für einen neuen Handler ist eine der folgenden Operationen auszuführen:

- Stellt zusätzlichen Speicherplatz für die Zuordnung bereit und springt anschließend zurück.

- Rufen Sie entweder **Abbrechen** oder **beenden**(`int`).

- Löst ein Objekt des Typs **bad_alloc** aus.

Standardmäßig wird für einen [new handler](../standard-library/new-typedefs.md#new_handler) ein Objekt des Typs `bad_alloc` ausgelöst. Ein NULL-Zeiger legt den neuen Standard-Handler fest.

Die Reihenfolge und Kontinuität von durch aufeinanderfolgende Aufrufe belegtem Speicherplatz `operator new`(**"size_t"**) ist nicht vorgegeben, wie die dort gespeicherten Anfangswerte.

Die zweite Funktion wird durch einen Placement-new-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Die Funktion lässt sich ersetzen, da das Programm eine Funktion mit dieser Funktionssignatur definieren kann, die die von der C++-Standardbibliothek definierte Standardversion ersetzt.

Das Standardverhalten ist zurückzugebenden `operator new`(`count`) die Funktion erfolgreich ausgeführt. Ansonsten gibt sie einen NULL-Zeiger zurück.

Die dritte Funktion wird durch einen Placement-**new**-Ausdruck der Form **new** ( *args*) T aufgerufen. In diesem Fall besteht *args* aus einem einzelnen Objektzeiger. Dies kann sich beim Erstellen eines Objekts an einer bekannten Adresse als nützlich erweisen. Die Funktion gibt *ptr* zurück.

Zum Freigeben von zugeordneten **new-Operator**, rufen Sie [Delete-Operator](../standard-library/new-operators.md#op_delete).

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

## <a name="op_new_arr"></a> operator new[]

Die Zuordnungsfunktion, die durch einen new-Ausdruck aufgerufen wird, um Speicherplatz für ein Array von Objekten zu belegen.

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);

void* operator new[](std::size_t count,
    const std::nothrow_t&) throw();

void* operator new[](std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parameter

*count*<br/>
Der Speicherplatz in Bytes, der für ein Array-Objekt belegt werden soll.

*ptr*<br/>
Der Zeiger, der zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Entweder ein Zeiger auf die niedrigste Byteadresse des neu belegten Speichers Oder *Ptr*.

### <a name="remarks"></a>Hinweise

Die erste Funktion wird durch einen `new[]`-Ausdruck aufgerufen, um `count`-Bytes im Speicher zu belegen, die genau auf alle Array-Objekte ausgerichtet sind, die höchstens diese Größe aufweisen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das erforderliche Verhalten ist dieselbe wie für [new-Operator](../standard-library/new-operators.md#op_new)(**"size_t"**). Standardmäßig wird `operator new`( `count`) zurückgegeben.

Die zweite Funktion wird durch einen Placement-`new[]`-Ausdruck aufgerufen, um genau auf alle Objekte dieser Größe ausgerichtete `count`-Bytes im Speicher zu belegen. Das Programm kann eine Funktion mit dieser Funktionssignatur definieren, die die von der C++-Standardbibliothek definierte Standardversion ersetzt. Das Standardverhalten ist zurückzugebenden **Operatornew**(`count`) die Funktion erfolgreich ausgeführt. Ansonsten gibt sie einen NULL-Zeiger zurück.

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

[\<new>](../standard-library/new.md)<br/>
