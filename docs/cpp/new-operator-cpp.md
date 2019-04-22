---
title: new-Operator (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: bcb7784e59966510970bd9b3ae0157ae982e462d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768067"
---
# <a name="new-operator-c"></a>new-Operator (C++)

Belegt Speicher für ein Objekt oder Array von Objekten des *Typname* aus dem freien Speicher und gibt einen typisierten Zeiger ungleich NULL zurück, auf das Objekt.

> [!NOTE]
>  Microsoft-Erweiterungen für C++-Komponente bietet Unterstützung für die **neue** Schlüsselwort, um eine Vtable-Slot Einträge hinzuzufügen. Weitere Informationen finden Sie unter [new (neuer Slot in Vtable)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>Syntax

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>Hinweise

Wenn Fehler auftreten, **neue** gibt NULL zurück oder löst eine Ausnahme aus; finden Sie unter [der neuen "und" delete](../cpp/new-and-delete-operators.md) für Weitere Informationen. Sie können dieses Standardverhalten ändern, indem eine benutzerdefinierte Ausnahmebehandlungsroutine schreiben und Aufrufen der [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) -Laufzeitbibliothek-Funktion mit dem Funktionsnamen als Argument.

Weitere Informationen zum Erstellen eines Objekts auf dem verwalteten Heap, finden Sie unter [Gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md).

Wenn **neue** wird verwendet, um Speicher für ein C++-Klassenobjekt zu reservieren, den Konstruktor des Objekts wird aufgerufen, nachdem der Speicher belegt wird.

Verwenden der [löschen](../cpp/delete-operator-cpp.md) Operator, um den mit belegten Arbeitsspeicher freizugeben. die **neue** Operator.

Im folgenden Beispiel wird ein zweidimensionales Array der Größe `dim` durch 10 zugewiesen und dann freigegeben. Beim Zuweisen eines mehrdimensionalen Arrays müssen alle Dimensionen mit Ausnahme der ersten Konstantenausdrücke sein, die zu positiven Werten ausgewertet werden. Die Arraydimension ganz links kann ein beliebiger Ausdruck sein, der zu einem positiven Wert ausgewertet wird. Beim Zuweisen eines Arrays mithilfe der **neue** Operator an mit, die erste Dimension kann 0 (null) sein, die **neue** Operator gibt einen eindeutigen Zeiger zurück.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

Die *Typname* dürfen nicht **const**, **flüchtige**, Klassendeklarationen oder Deklarationen einer Enumeration. Daher ist der folgende Ausdruck ungültig:

```cpp
volatile char *vch = new volatile char[20];
```

Die **neue** Operator keine Referenztypen zugewiesen, da diese keine Objekte sind.

Die **neue** Operator kann nicht zum Zuweisen einer Funktion verwendet werden, aber es kann verwendet werden, um Funktionen Zeiger zuzuordnen. Im folgenden Beispiel wird ein Array von sieben Zeigern auf Funktionen, die ganze Zahlen zurückgeben, zugewiesen und dann freigegeben.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

Wenn Sie den Operator verwenden **neue** ohne zusätzliche Argumente, und die Kompilierung mit der [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md), oder [/EHs](../build/reference/eh-exception-handling-model.md) Option, um der Compiler wird Generieren von Code zum Aufrufen des Operators **löschen** Wenn der Konstruktor eine Ausnahme auslöst.

Die folgende Liste beschreibt die Grammatikelemente von **neue**:

*placement*<br/>
Bietet eine Möglichkeit der Übergabe zusätzlicher Argumente, wenn Sie überladen **neue**.

*type-name*<br/>
Gibt den zuzuweisenden Typ an. Es kann entweder ein integrierter oder ein benutzerdefinierter Typ sein. Eine komplizierte Typspezifikation können Sie in Klammern einschließen, um die Reihenfolge der Bindung zu erzwingen.

*initializer*<br/>
Stellt einen Wert für das initialisierte Objekt bereit. Für Arrays können keine Initialisierer angegeben werden. Die **neue** -Operator erstellt Arrays von Objekten, nur dann, wenn die Klasse über einen Standardkonstruktor verfügt.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden ein Zeichenarray und ein Objekt der Klasse `CName` zugewiesen und dann wieder freigegeben.

```cpp
// expre_new_Operator.cpp
// compile with: /EHsc
#include <string.h>

class CName {
public:
   enum {
      sizeOfBuffer = 256
   };

   char m_szFirst[sizeOfBuffer];
   char m_szLast[sizeOfBuffer];

public:
   void SetName(char* pszFirst, char* pszLast) {
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);
   }

};

int main() {
   // Allocate memory for the array
   char* pCharArray = new char[CName::sizeOfBuffer];
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");

   // Deallocate memory for the array
   delete [] pCharArray;
   pCharArray = NULL;

   // Allocate memory for the object
   CName* pName = new CName;
   pName->SetName("Firstname", "Lastname");

   // Deallocate memory for the object
   delete pName;
   pName = NULL;
}
```

## <a name="example"></a>Beispiel

Bei Verwendung die neuen Positionierungsform des der **neue** Operator an, das Formular mit Argumenten zuzüglich der Größe der Zuordnung, der Compiler unterstützt keine Positionierungsform des der **löschen** Operator Wenn die Konstruktor löst eine Ausnahme aus. Zum Beispiel:

```cpp
// expre_new_Operator2.cpp
// C2660 expected
class A {
public:
   A(int) { throw "Fail!"; }
};
void F(void) {
   try {
      // heap memory pointed to by pa1 will be deallocated
      // by calling ::operator delete(void*).
      A* pa1 = new A(10);
   } catch (...) {
   }
   try {
      // This will call ::operator new(size_t, char*, int).
      // When A::A(int) does a throw, we should call
      // ::operator delete(void*, char*, int) to deallocate
      // the memory pointed to by pa2.  Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.

      A* pa2 = new(__FILE__, __LINE__) A(20);
   } catch (...) {
   }
}

int main() {
   A a;
}
```

## <a name="initializing-object-allocated-with-new"></a>Initialisieren von mit „new“ zugeordneten Objekten

Eine optionale *Initialisierer* Feld befindet sich in der Grammatik für die **neue** Operator. Dadurch können neue Objekte mit benutzerdefinierten Konstruktoren initialisiert werden. Weitere Informationen dazu, wie die Initialisierung durchgeführt wird, finden Sie unter [Initialisierer](../cpp/initializers.md). Das folgende Beispiel veranschaulicht, wie Sie einen Initialisierungsausdruck mit dem **neue** Operator:

```cpp
// expre_Initializing_Objects_Allocated_with_new.cpp
class Acct
{
public:
    // Define default constructor and a constructor that accepts
    //  an initial balance.
    Acct() { balance = 0.0; }
    Acct( double init_balance ) { balance = init_balance; }
private:
    double balance;
};

int main()
{
    Acct *CheckingAcct = new Acct;
    Acct *SavingsAcct = new Acct ( 34.98 );
    double *HowMuch = new double ( 43.0 );
    // ...
}
```

In diesem Beispiel wird das Objekt `CheckingAcct` wird zugeordnet, mit der **neue** -Operator, aber keine standardinitialisierung angegeben ist. Deshalb wird der Standardkonstruktor für die `Acct()`-Klasse aufgerufen. Anschließend wird das Objekt `SavingsAcct` auf die gleiche Weise zugeordnet, mit der Ausnahme, dass es explizit mit 34,98 initialisiert wird. Da 34.98 den Typ aufweist **doppelte**, der Konstruktor, der ein des Typs Argument wird aufgerufen, um die Initialisierung zu bearbeiten. Schließlich wird der Nichtklassentyp `HowMuch` mit 43,0 initialisiert.

Wenn ein Objekt eines Klassentyps ist, und diese Klasse verfügt über Konstruktoren (wie im vorherigen Beispiel), kann das Objekt initialisiert werden, indem die **neue** Operator nur dann, wenn eine der folgenden Bedingungen erfüllt ist:

- Die Argumente, die im Initialisierer bereitgestellt werden, stimmen mit denen eines Konstruktors überein.

- Die Klasse verfügt über einen Standardkonstruktor (einen Konstruktor, der ohne Argumente aufgerufen werden kann).

Keine Initialisierung pro Element explizit ausgeführt werden kann, beim Zuordnen von mithilfe Arrays der **neue** Operator; nur der Standardkonstruktor, falls vorhanden, aufgerufen wird. Finden Sie unter [Standardargumente](../cpp/default-arguments.md) für Weitere Informationen.

Wenn die speicherbelegung fehlschlägt (**new-Operator** gibt einen Wert von 0 zurück), keine Initialisierung ausgeführt. Dies schützt vor Versuchen, Daten zu initialisieren, die nicht vorhanden sind.

Wie bei Funktionsaufrufen ist auch bei initialisierten Ausdrücken die Reihenfolge der Auswertung nicht festgelegt. Darüber hinaus sollten Sie sich nicht darauf verlassen, dass diese Ausdrücke vollständig ausgewertet werden, bevor die Speicherbelegung ausgeführt wird. Wenn die speicherbelegung fehlschlägt und die **neue** Operator gibt 0 (null) zurück, die einige Ausdrücke im Initialisierer möglicherweise nicht vollständig ausgewertet.

## <a name="lifetime-of-objects-allocated-with-new"></a>Lebensdauer von mit „new“ zugeordneten Objekten

Mit zugeordneten Objekten der **neue** Operator werden nicht gelöscht werden, wenn der Bereich, in dem sie definiert sind, beendet wird. Da die **neue** Operator gibt einen Zeiger auf die er weist Objekte zurück, das Programm muss einen Zeiger mit passendem Gültigkeitsbereich den Zugriff auf diese Objekte definieren. Zum Beispiel:

```cpp
// expre_Lifetime_of_Objects_Allocated_with_new.cpp
// C2541 expected
int main()
{
    // Use new operator to allocate an array of 20 characters.
    char *AnArray = new char[20];

    for( int i = 0; i < 20; ++i )
    {
        // On the first iteration of the loop, allocate
        //  another array of 20 characters.
        if( i == 0 )
        {
            char *AnotherArray = new char[20];
        }
    }

    delete [] AnotherArray; // Error: pointer out of scope.
    delete [] AnArray;      // OK: pointer still in scope.
}
```

Sobald der Zeiger `AnotherArray` den Gültigkeitsbereich in dem Beispiel verlässt, kann das Objekt nicht mehr gelöscht werden.

## <a name="how-new-works"></a>Funktionsweise von „new“

Die *Zuweisungsausdruck* : der Ausdruck enthält das **neue** Operator – bewirkt drei Dinge:

- Sucht und reserviert Speicher für das zuzuweisende Objekt bzw. die zuzuweisenden Objekte. Nach Abschluss dieser Phase wird die richtige Menge an Speicherplatz zugewiesen. Es handelt sich jedoch noch nicht um ein Objekt.

- Initialisiert das/die Objekt(e). Sobald die Initialisierung abgeschlossen wurde, sind genügend Informationen vorhanden, damit der zugeordnete Speicher ein Objekt sein kann.

- Gibt ein Zeiger auf die Objekte eines Zeigertyps abgeleitet *neue Typname* oder *Typname*. Das Programm verwendet diesen Zeiger, um auf das neu zugeordnete Objekt zuzugreifen.

Die **neue** -Operator Ruft die Funktion **new-Operator**. Für Arrays jeglichen Typs und für Objekte, die nicht von **Klasse**, **Struktur**, oder **Union** Typen, die globale Funktion **:: Operator neue**, ist wird aufgerufen, um Speicher zuzuweisen. Klassentypobjekte können ihre eigenen definieren **new-Operator** statische Memberfunktion auf Basis einer pro-Klasse.

Wenn der Compiler erkennt die **neue** Operator, um einem Objekt des Typs zugewiesen werden **Typ**, gibt er einen Aufruf von `type` **:: new-Operator (Sizeof (** `type` **))** oder, wenn keine benutzerdefinierte **new-Operator** definiert ist, **:: new-Operator (Sizeof (** `type` **))**. Aus diesem Grund die **neue** Operator kann die richtige Menge an Arbeitsspeicher zugeteilt, für das Objekt.

> [!NOTE]
>  Das Argument für **new-Operator** ist vom Typ `size_t`. Dieser Typ definiert, \<direct.h >, \<malloc.h >, \<memory.h >, \<search.h >, \<stddef.h >, \<stdio.h >, \<stdlib.h >, \<string.h >, und \<time.h >.

Eine Option in der Grammatik ermöglicht die Angabe eines *Platzierung* (finden Sie in der Grammatik für [neuer Operator](../cpp/new-operator-cpp.md)). Die *Platzierung* Parameter kann verwendet werden, nur für benutzerdefinierte Implementierungen der **new-Operator**; damit können weitere Informationen zu übergebenden **new-Operator**. Ein Ausdruck mit einer *Platzierung* Feld, z. B. `T *TObject = new ( 0x0040 ) T;` in übersetzt `T *TObject = T::operator new( sizeof( T ), 0x0040 );` Wenn Klasse T Memberoperator neu, um andernfalls hat `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.

Die ursprüngliche Absicht des der *Platzierung* Feld wurde, können Objekte, die an benutzerspezifischen Adressen zugeordnet werden.

> [!NOTE]
>  Obwohl das vorherige Beispiel nur ein Argument im zeigt die *Platzierung* Feld, es gibt keine Einschränkung auf wie viele zusätzliche Argumente können, um übergeben werden **new-Operator** auf diese Weise.

Auch wenn **new-Operator** definiert wurde für einen Klassentyp, der globale Operator verwendet werden kann, mit dem Formular dieses Beispiels:

```cpp
T *TObject =::new TObject;
```

Der Bereichsauflösungsoperator (`::`) erzwingt die Verwendung des globalen **neue** Operator.

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[neue und "delete"](../cpp/new-and-delete-operators.md)