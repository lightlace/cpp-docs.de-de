---
title: Destruktoren (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b16230d612ea7304e8bc06a9810838ce3f42ac8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405648"
---
# <a name="destructors-c"></a>Destruktoren (C++)

Ein Destruktor ist eine Memberfunktion, die automatisch aufgerufen wird, wenn das Objekt den Gültigkeitsbereich verlässt oder ausdrücklich durch einen Aufruf von zerstört wird **löschen**. Ein Destruktor hat den gleichen Namen wie die Klasse, die vorangestellten Tilde (`~`). Beispielsweise wird der Destruktor für die `String`-Klasse folgendermaßen deklariert: `~String()`.

Wenn Sie keinen Destruktor definieren, wird der Compiler ein Standardmanifest bereit; für viele Klassen ist dies ausreichend. Sie müssen nur einen benutzerdefinierten Destruktor definieren, wenn die Klasse Handles auf Systemressourcen speichert, die freigegeben werden müssen, oder Zeiger, die den Arbeitsspeicher besitzen beide zeigen auf.

Betrachten Sie die folgende Deklaration einer `String`-Klasse.

```cpp
// spec1_destructors.cpp
#include <string.h>

class String {
public:
   String( char *ch );  // Declare constructor
   ~String();           //  and destructor.
private:
   char    *_text;
   size_t  sizeOfText;
};

// Define the constructor.
String::String( char *ch ) {
   sizeOfText = strlen( ch ) + 1;

   // Dynamically allocate the correct amount of memory.
   _text = new char[ sizeOfText ];

   // If the allocation succeeds, copy the initialization string.
   if( _text )
      strcpy_s( _text, sizeOfText, ch );
}

// Define the destructor.
String::~String() {
   // Deallocate the memory that was previously reserved
   //  for this string.
   if (_text)
      delete[] _text;
}

int main() {
   String str("The piper in the glen...");
}
```

Im vorherigen Beispiel ist der Destruktor `String::~String` verwendet die **löschen** Operator, um den Speicherplatz, der dynamisch Textspeicher zugeordnet freizugeben.

## <a name="declaring-destructors"></a>Deklarieren von Destruktoren

Destruktoren sind Funktionen mit dem gleichen Namen wie die Klasse, jedoch mit einer vorangestellten Tilde (`~`).

Mehrere Regeln bestimmen die Deklaration von Destruktoren. Destruktoren:

- Akzeptieren keine Argumente.

- Ohne einen Wert zurückzugeben (oder **"void"**).

- Kann nicht deklariert werden, als **const**, **flüchtige**, oder **statische**. Allerdings aufgerufen werden, für die Zerstörung von Objekten als deklariert **const**, **flüchtige**, oder **statische**.

- Kann als deklariert **virtuellen**. Mithilfe von virtuellen Destruktoren können Sie Objekte zerstören, ohne ihren Typ zu kennen. Der richtige Destruktor für das Objekt wird mithilfe des Mechanismus der virtuellen Funktion aufgerufen. Destruktoren können auch als rein virtuelle Funktionen für abstrakte Klassen deklariert werden.

## <a name="using-destructors"></a>Verwenden von Destruktoren

Destruktoren werden aufgerufen, wenn eines der folgenden Ereignisse eintritt:

- Ein lokales (automatisches) Objekt mit Blockbereich verlässt den Gültigkeitsbereich.

- Ein Objekt mit reserviert die **neue** Operator wird explizit freigegeben mit **löschen**.

- Die Lebensdauer eines temporären Objekts endet.

- Ein Programm endet, und es sind globale oder statische Objekte vorhanden.

- Der Destruktor wird unter Verwendung des vollqualifizierten Namens der Funktion explizit aufgerufen.

Destruktoren können beliebig Klassenmemberfunktionen aufrufen und auf Klassenmemberdaten zugreifen.

Es gibt zwei Einschränkungen für die Verwendung von Destruktoren aus:

- Die Adresse ist nicht möglich.

- Abgeleitete Klassen erben nicht den Destruktor der Basisklasse.

## <a name="order-of-destruction"></a>Reihenfolge der Destruktion

Wenn ein Objekt den gültigen Bereich verlässt oder gelöscht wird, lautet die Reihenfolge der Ereignisse bei seiner vollständigen Zerstörung wie folgt:

1. Der Destruktor der Klasse wird aufgerufen, und der Text der Destruktorfunktion wird ausgeführt.

1. Destruktoren für nicht statische Memberobjekte werden in umgekehrter Reihenfolge aufgerufen, in der sie in der Klassendeklaration stehen. Die optionale Memberinitialisierungsliste, die verwendet werden, in der Konstruktion dieser Member hat keine Auswirkungen auf die Reihenfolge der Konstruktion oder Zerstörung.

1. Destruktoren für nicht virtuelle Basisklassen werden in umgekehrter Reihenfolge der Deklaration aufgerufen.

1. Destruktoren für virtuelle Basisklassen werden in umgekehrter Reihenfolge der Deklaration aufgerufen.

```cpp
// order_of_destruction.cpp
#include <stdio.h>

struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };

struct B1      { ~B1() { printf("B1 dtor\n"); } };
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };

int main() {
   A1 * a = new A3;
   delete a;
   printf("\n");

   B1 * b = new B3;
   delete b;
   printf("\n");

   B3 * b2 = new B3;
   delete b2;
}

Output: A3 dtor
A2 dtor
A1 dtor

B1 dtor

B3 dtor
B2 dtor
B1 dtor
```

### <a name="virtual-base-classes"></a>Virtuelle Basisklassen

Destruktoren für virtuelle Basisklassen werden in umgekehrter Reihenfolge ihrer Darstellung in einem gerichteten azyklischen Diagramm aufgerufen (Durchlauf vom tiefsten Punkt nach oben, von links nach rechts, Postorder-Durchlauf). Die folgende Abbildung stellt ein Vererbungsdiagramm dar.

![Vererbungsdiagramm, der virtuellen Basisklassen](../cpp/media/vc392j1.gif "vc392J1")

Vererbungsdiagramm mit virtuellen Basisklassen

Im Folgenden werden die Klassenköpfe für die in der Abbildung dargestellten Klassen aufgeführt.

```cpp
class A
class B
class C : virtual public A, virtual public B
class D : virtual public A, virtual public B
class E : public C, public D, virtual public B
```

Um die Reihenfolge zum Löschen der virtuellen Basisklassen eines Objekts vom Typ `E` zu bestimmen, erstellt der Compiler eine Liste mithilfe des folgenden Algorithmus:

1. Durchlaufen Sie das Diagramm von links, und beginnen Sie mit dem tiefsten Punkt im Diagramm (in diesem Fall `E`).

1. Führen Sie Durchläufe von links aus, bis alle Knoten aufgerufen wurden. Notieren Sie den Namen des aktuellen Knotens.

1. Rufen Sie erneut den vorherigen Knoten auf (nach unten und rechts), um festzustellen, ob es sich bei dem gemerkten Knoten um eine virtuelle Basisklasse handelt.

1. Falls der gemerkte Knoten eine virtuelle Basisklasse ist, prüfen Sie anhand der Liste, ob diese bereits erfasst ist. Handelt es sich nicht um eine Basisklasse, können Sie dies ignorieren.

1. Sofern der gemerkte Knoten noch nicht in der Liste vorhanden ist, fügen Sie ihn unten hinzu.

1. Durchlaufen Sie das Diagramm nach oben und entlang des nächsten Pfads nach rechts.

1. Wechseln Sie zu Schritt 2.

1. Wenn der letzte nach oben zeigende Pfeil angezeigt wird, notieren Sie den Namen des aktuellen Knotens.

1. Gehen Sie zu Schritt 3.

1. Setzen Sie diesen Vorgang fort, bis der untere Knoten wieder der aktuelle Knoten ist.

Daher lautet für die Klasse `E` die Reihenfolge der Löschung wie folgt:

1. Die nicht virtuelle Basisklasse `E`.

1. Die nicht virtuelle Basisklasse `D`.

1. Die nicht virtuelle Basisklasse `C`.

1. Die virtuelle Basisklasse `B`.

1. Die virtuelle Basisklasse `A`.

Dieser Prozess erzeugt eine sortierte Liste mit eindeutigen Einträgen. Kein Klassenname wird zweimal angezeigt. Sobald die Liste erstellt ist, wird sie in umgekehrter Reihenfolge durchlaufen, und der Destruktor wird für jede Klasse in der Liste (von der letzten bis zu ersten) aufgerufen.

In erster Linie ist die Reihenfolge zum Erstellen oder Löschen wichtig, wenn Konstruktoren oder Destruktoren einer Klasse darauf basieren, dass die andere Komponente erstellt wird oder länger vorhanden ist – beispielsweise wenn der Destruktor für `A` (in der obigen Abbildung) darauf basiert, dass `B` bei der Codeausführung noch vorhanden ist (oder umgekehrt).

Folglich sind diese gegenseitigen Abhängigkeiten zwischen den Klassen in einem Vererbungsdiagramm grundsätzlich gefährlich, da später abgeleitete Klassen den am weitesten links stehenden Pfad ändern und somit auch die Reihenfolge zum Erstellen und Löschen verändern können.

### <a name="non-virtual-base-classes"></a>Nicht virtuelle Basisklassen

Die Destruktoren für nicht virtuelle Basisklassen werden in umgekehrter Reihenfolge aufgerufen, in denen die Namen der Basisklasse deklariert werden. Betrachten Sie die folgende Klassendeklaration:

```cpp
class MultInherit : public Base1, public Base2
...
```

Im vorherigen Beispiel wird der Destruktor für `Base2` vor dem Destruktor für `Base1` aufgerufen.

## <a name="explicit-destructor-calls"></a>Explizite Destruktoraufrufe

Einen Destruktor explizit aufzurufen, ist selten notwendig. Allerdings kann es hilfreich sein, eine Bereinigung von Objekten auszuführen, die an den absoluten Adressen platziert werden. Diese Objekte werden im Allgemeinen zugeordnet mit einem benutzerdefinierten **neue** Operator, der ein platzierungsargument akzeptiert. Die **löschen** Operator kann nicht diesen Arbeitsspeicher freigeben, da es nicht aus dem freien Speicher zugeordnet wird (Weitere Informationen finden Sie unter [der neuen "und" delete](../cpp/new-and-delete-operators.md)). Ein Aufruf des Destruktors kann jedoch eine geeignete Bereinigung ausführen. Mit einer der folgenden Anweisungen können Sie den Destruktor für ein Objekt `s` der Klasse `String` explizit aufrufen:

```cpp
s.String::~String();     // non-virtual call
ps->String::~String();   // non-virtual call

s.~String();       // Virtual call
ps->~String();     // Virtual call
```

Die Notation für explizite Aufrufe von Destruktoren (zuvor gezeigt) kann unabhängig davon verwendet werden, ob der Typ einen Destruktor definiert. Dies ermöglicht Ihnen solche expliziten Aufrufe, ohne zu wissen, ob ein Destruktor für den Typ definiert ist. Ein expliziter Aufruf von einem Destruktor, wenn keiner definiert ist, hat keine Auswirkungen.