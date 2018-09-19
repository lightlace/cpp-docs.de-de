---
title: Wert Typsemantik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 72dc6a613616d13e9ff92e8af0c39c63dfe63162
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413795"
---
# <a name="value-type-semantics"></a>Werttypsemantik

Werttypsemantik haben von Managed Extensions für C++ in Visual C++ geändert.

Hier ist der kanonische einfachen Werttyp in Managed Extensions für C++-Spezifikation verwendet:

```
__value struct V { int i; };
__gc struct R { V vr; };
```

In Managed Extensions können wir haben vier syntaktische Varianten eines Werttyps (wobei sind Formulare, 2 und 3 gleich semantisch):

```
V v = { 0 };       // Form (1)
V *pv = 0;         // Form (2) an implicit form of (3)
V __gc *pvgc = 0;  // Form (3)
__box V* pvbx = 0; // Form (4) must be local
```

## <a name="invoking-inherited-virtual-methods"></a>Geerbte virtuelle Methoden aufrufen

`Form (1)` ist der kanonische, und es ist ausreichend gut verstanden, außer wenn jemand versucht, eine geerbte virtuelle Methode aufrufen, wie z. B. `ToString()`. Zum Beispiel:

```
v.ToString(); // error!
```

Um diese Methode aufzurufen, da es nicht in überschrieben wird `V`, der Compiler muss Zugriff auf die zugeordnete virtuelle Tabelle der Basisklasse haben. Da die Werte ohne die zugeordneten Zeiger auf die virtuelle Tabelle (Vptr) im Zustandsspeicher werden, dies erfordert, dass `v` geschachtelt werden. Klicken Sie in der Managed Extensions-Sprachentwurf implizites Boxing wird nicht unterstützt, jedoch muss explizit angegeben werden durch den Programmierer, wie in

```
__box( v )->ToString(); // Managed Extensions: note the arrow
```

Ihr Hauptzweck dieses Entwurfs ist pädagogischer Natur: zugrunde liegende Mechanismus muss sichtbar gemacht werden, damit sie verstehen, die "Kosten" fest, der eine Instanz in ihrem Werttyp nicht bereitgestellt wird. Wurden `V` enthält eine Instanz von `ToString`, das Boxing wäre nicht erforderlich.

Die lexikalische Komplexität explizit boxing des Objekts, aber nicht die zugrunde liegenden Kosten für das Boxing selbst wird in der neuen Syntax entfernt:

```
v.ToString(); // new syntax
```

jedoch möglicherweise irreführende Klassen-Designer, die Kosten für nicht müssen explizite Instanz einer bereitgestellten der `ToString` -Methode im `V`. Der Grund für implizites Boxing ist, dass es gibt zwar in der Regel nur eine Klassen-Designer, es eine unbegrenzte Anzahl von Benutzern gibt, none, von denen müssten die Freiheit gibt, ändern Sie `V` um explizite Feld möglicherweise schwer zu vermeiden.

Kriterien, um zu bestimmen, ob eine überschreibende Instanz der zu `ToString` innerhalb einer Klasse muss die Häufigkeit und Position Verwendungen. Wenn sie nur sehr selten aufgerufen wird, ist natürlich wenig Vorteile in ihrer Definition. Auf ähnliche Weise wird es in nicht leistungsfähig Bereiche der Anwendung aufgerufen wird, wird es auch nicht merklich auf die allgemeine Leistung der Anwendung hinzufügen. Alternativ kann eine ein Trackinghandle für den geschachtelten Wert beibehalten und Aufrufe über den Handle kein Boxing erfordern.

## <a name="there-is-no-longer-a-value-class-default-constructor"></a>Es ist nicht mehr einen Standard-Konstruktor von Wert-Klasse

Ein weiterer Unterschied mit einem Werttyp zwischen Managed Extensions und der neuen Syntax ist das Entfernen der Unterstützung für einen standardmäßigen Konstruktor. Dies ist, da es Situationen, in denen während der Ausführung in dem die CLR eine Instanz des Werttyps erstellen kann gibt, ohne Aufrufen des Konstruktors standardmäßig zugeordnet ist. Der Versuch in Managed Extensions, um einen standardmäßigen Konstruktor in einen Werttyp zu unterstützen kann, also in der Praxis nicht garantiert werden. Angesichts dieser fehlen garantiert, wurde es erschien, besser sein, die Unterstützung vollständig löschen, anstatt in der Anwendung nicht deterministisch ist.

Dies ist keine so schlechte Idee, wie es zunächst scheint. Dies ist, da jedes Objekt ein Werttyp automatisch auf NULL gesetzt ist (d. h. jeder Typ wird auf seinen Standardwert initialisiert). Daher sind die Mitglieder einer lokalen Instanz nie nicht definiert. In diesem Sinn der Verlust der Fähigkeit, definieren Sie einen trivialen Standardkonstruktor ist wirklich keine Verlust an alle – und in der Tat ist effizienter, wenn von der CLR ausgeführt.

Das Problem ist, wenn ein Benutzer von Managed Extensions einen nicht trivialen Standardkonstruktor definiert. Dies hat keine Zuordnung in der neuen Syntax. Der Code im Konstruktor müssen in eine benannte Initialisierungsmethode migriert werden, die explizit vom Benutzer aufgerufen werden müssen.

Die Deklaration eines Objekts vom Typ Wert in der neuen Syntax ist andernfalls nicht geändert. Der Nachteil dieses ist, dass der Zugriff auf Typen mit Werten aus den folgenden Gründen nicht für die Einbindung der systemeigenen Typen sind:

- Es gibt keine Unterstützung für einen Destruktor in einen Werttyp. Es ist, also keine Möglichkeit, eine Reihe von Aktionen, die ausgelöst wird, die Lebensdauer eines Objekts am Ende zu automatisieren.

- Eine systemeigene Klasse kann als Zeiger, der dann auf dem systemeigenen Heap zugeordnet ist, nur innerhalb eines verwalteten Typs enthalten sein.

Wir würden gerne eine kleine systemeigene Klasse in einen Werttyp statt in einen Verweistyp handelt, eine doppelte Heapzuweisung zu vermeiden umschließen: systemeigenen Heap, den systemeigenen Typ und die CLR-Heap, den verwalteten Wrapper enthalten soll. Einschließen einer systemeigenen Klasse innerhalb eines Werttyps können Sie den verwalteten Heap zu vermeiden, jedoch bietet keine Möglichkeit, um die Freigabe von Speicher auf dem systemeigenen Heap zu automatisieren. Verweistypen sind die einzigen verwalteten Typen, in dem nicht trivialen native Klassen zu umschließen.

## <a name="interior-pointers"></a>Inneren Zeigern

`Form (2)` und `Form (3)` höher können adressieren fast alles in dieser Umgebung oder bei der nächsten (d. h. alles verwaltet oder systemeigen). Also beispielsweise Folgendes in Managed Extensions dürfen:

```
__value struct V { int i; };
__gc struct R { V vr; };

V v = { 0 };  // Form (1)
V *pv = 0;  // Form (2)
V __gc *pvgc = 0;  // Form (3)
__box V* pvbx = 0;  // Form (4)

R* r;

pv = &v;            // address a value type on the stack
pv = __nogc new V;  // address a value type on native heap
pv = pvgc;          // we are not sure what this addresses
pv = pvbx;          // address a boxed value type on managed heap
pv = &r->vr;        // an interior pointer to value type within a
                    //    reference type on the managed heap
```

Also eine `V*` können einen Speicherort in einem lokalen Block erfüllen (und aus diesem Grund können Verbleibend) im globalen Gültigkeitsbereich, in dem systemeigenen heap (z. B., wenn das Objekt, das es adressiert bereits gelöscht wurde), in dem CLR-Heap (und daher wird nachverfolgt werden, wenn er es sollte verlagert werden während der Garbagecollection), und klicken Sie in das Innere eines Verweis-Objekts, auf dem CLR-Heap (ein innerer Zeiger, wie diese aufgerufen wird, ist ebenfalls transparent nachverfolgt).

In Managed Extensions besteht keine Möglichkeit, um die native Aspekte der trennen eine `V*`; d. h. es wird behandelt inklusiv behandelt die Möglichkeit eines Objekts oder Unterobjekts auf dem verwalteten Heap zu adressieren.

In der neuen Syntax ein Werttypzeiger ist in zwei Arten berücksichtigt: `V*`, der auf nicht-CLR-Heap-Speicherorte und der inneren Zeiger beschränkt ist `interior_ptr<V>`, die ermöglicht jedoch eine Adresse innerhalb des verwalteten Heaps ist nicht erforderlich.

```
// may not address within managed heap
V *pv = 0;

// may or may not address within managed heap
interior_ptr<V> pvgc = nullptr;
```

`Form (2)` und `Form (3)` Zuordnen von Managed Extensions `interior_ptr<V>`. `Form (4)` ist ein Trackinghandle. Es behandelt das gesamte Objekt, das auf dem verwalteten Heap geschachtelt worden ist. Es wird übersetzt in der neuen Syntax in einem `V^`,

```
V^ pvbx = nullptr; // __box V* pvbx = 0;
```

Die folgenden Deklarationen in Managed Extensions, die alle inneren Zeigern in der neuen Syntax zugeordnet werden soll. (sie sind Werttypen, die innerhalb der `System` Namespace.)

```
Int32 *pi;   // => interior_ptr<Int32> pi;
Boolean *pb; // => interior_ptr<Boolean> pb;
E *pe;       // => interior_ptr<E> pe; // Enumeration
```

Die integrierten Typen werden nicht verwaltete Typen berücksichtigt, obwohl sie als Alias für die Typen im dienen der `System` Namespace. Daher gelten die folgenden Zuordnungen zwischen Managed Extensions und der neuen Syntax:

```
int * pi;     // => int* pi;
int __gc * pi2; // => interior_ptr<int> pi2;
```

Beim Übersetzen einer `V*` in das vorhandene Programm, die konservativste Strategie ist, immer zum Aktivieren einer `interior_ptr<V>`. Dies ist wie die Datei in Managed Extensions behandelt wurde. In der neuen Syntax der Programmierer hat die Möglichkeit, einen Werttyp an nicht verwalteten Heap-Adressen einschränken, durch Angabe `V*` statt eines inneren Zeigers. Wenn Sie beim Übersetzen des Programms an, Sie können alle Verwendungen einen transitiven Abschluss und achten Sie darauf, dass keine zugewiesene Adresse auf dem verwalteten Heap ist, dann seinen Arbeitsplatz verlässt als `V*` ist in Ordnung.

## <a name="pinning-pointers"></a>Festhalten von Zeigern

Der Garbage Collector kann optional Objekte verschieben, die sich auf die CLR-Heap an verschiedene Positionen im Heap, in der Regel während einer Komprimierungsphase befinden. Diese Bewegung ist kein Problem, Nachverfolgen von Handles, Nachverfolgungsverweisen und inneren Zeigern, die diese Entitäten transparent zu aktualisieren. Diese Bewegung ist jedoch ein Problem, wenn der Benutzer die Adresse eines Objekts auf dem CLR-Heap außerhalb der Common Language Runtime-Umgebung überschritten hat. In diesem Fall ist die flüchtige Bewegung des Objekts ein Laufzeitfehler verursachen. Auf ausgenommen Objekte wie diese verschoben werden, wir müssen lokal heften Sie sie an ihrem Speicherort für den Wertebereich außerhalb verwendet.

In Managed Extensions eine *festen Zeiger* wird deklariert, indem eine Zeigerdeklaration mit der `__pin` Schlüsselwort. Hier ist ein Beispiel aus der Spezifikation von Managed Extensions etwas geändert:

```
__gc struct H { int j; };

int main()
{
   H * h = new H;
   int __pin * k = & h -> j;

   // ...
};
```

In der neuen Sprachentwurf wird ein fester Zeiger mit Syntax, die analog zu der ein innerer Zeiger deklariert.

```
ref struct H
{
public:
   int j;
};

int main()
{
   H^ h = gcnew H;
   pin_ptr<int> k = &h->j;

   // ...
}
```

Ein fester Zeiger in der neuen Syntax ist ein Sonderfall eines inneren Zeigers. Die ursprünglichen Einschränkungen für einen festen Zeiger bleiben. Angenommen, es kann nicht als Parameter verwendet werden oder Rückgabetyp einer Methode; Es kann nur auf ein lokales Objekt deklariert werden. Eine Anzahl von zusätzlichen Einschränkungen wurden jedoch in der neuen Syntax hinzugefügt.

Der Standardwert, der einen festen Zeiger ist `nullptr`, nicht `0`. Ein `pin_ptr<>` kann nicht initialisiert oder zugewiesen werden `0`. Alle Zuweisungen `0` in vorhandenem Code in geändert werden müssen `nullptr`.

Ein fester Zeiger in Managed Extensions wurde zugelassen, um ein ganzes Objekt, wie im folgenden Beispiel stammt aus der Managed Extensions-Spezifikation zu beheben:

```
__gc class G {
public:
   void incr(int* pi) { pi += 1; }
};
__gc struct H { int j; };
void f( G * g ) {
   H __pin * pH = new H;
   g->incr(& pH -> j);
};
```

In der neuen Syntax wird das gesamte Objekt befestigen zurückgegeben, indem die `new` Ausdruck wird nicht unterstützt. Stattdessen muss die Adresse des inneren Elements angeheftet werden. Ein auf ein Objekt angewendeter

```
ref class G {
public:
   void incr(int* pi) { *pi += 1; }
};
ref struct H { int j; };
void f( G^ g ) {
   H ^ph = gcnew H;
   Console::WriteLine(ph->j);
   pin_ptr<int> pj = &ph->j;
   g->incr(  pj );
   Console::WriteLine(ph->j);
}
```

## <a name="see-also"></a>Siehe auch

[Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)<br/>
[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)