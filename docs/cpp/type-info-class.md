---
title: type_info-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 169a54373c66c2f6b33d71e68500c3bf85e871c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560718"
---
# <a name="typeinfo-class"></a>type_info-Klasse

Die **Type_info** Klasse beschreibt die Typinformationen, die innerhalb des Programms vom Compiler generiert werden. Objekte dieser Klasse speichern effektiv einen Zeiger auf einen Namen für den Typ. Die **Type_info** Klasse speichert auch einen codierten Wert für das Vergleichen von zwei Typen für Gleichheit oder Sortierreihenfolge. Die Codierungsregeln und die Sortierreihenfolge für Typen sind nicht spezifiziert und können je nach Programm unterschiedlich sein.

Die `<typeinfo>` Headerdatei-Druckertreiber eingeschlossen werden muss die **Type_info** Klasse. Die Schnittstelle für die **Type_info** -Klasse ist:

```cpp
class type_info {
public:
    virtual ~type_info();
    size_t hash_code() const
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

Objekte können nicht instanziiert werden die **Type_info** -Klasse direkt verwenden, da die Klasse nur einen privaten Kopierkonstruktor aufweist. Die einzige Möglichkeit, ein (temporäres) **Type_info** Objekt ist die Verwendung der [Typeid](../cpp/typeid-operator.md) Operator. Da der Zuweisungsoperator auch privat ist, Sie nicht kopieren oder zuweisen können Objekte der Klasse **Type_info**.

`type_info::hash_code` definiert eine Hashfunktion, die geeignet ist, Werte des Typs **Typeinfo** einer Verteilung von Indexwerten.

Die Operatoren `==` und `!=` können verwendet werden, um auf Gleichheit und Ungleichheit verglichen werden soll, mit anderen **Type_info** -Objekten.

Es gibt keine Verbindung zwischen der Sortierreihenfolge von Typen und Vererbungsbeziehungen. Verwenden der `type_info::before` Member-Funktion, um die Sortierreihenfolge von Typen zu ermitteln. Es gibt keine Garantie, `type_info::before` ergibt das gleiche Ergebnis in verschiedenen Programmen oder sogar von verschiedenen Ausführungen desselben Programms. Auf diese Weise `type_info::before` ist vergleichbar mit dem Address-of `(&)` Operator.

Die `type_info::name` Memberfunktion gibt ein `const char*` auf eine Null-terminierte Zeichenfolge, die den lesbaren Namen des Typs darstellt. Der Speicher, auf den gezeigt wird, wird zwischengespeichert und sollte nie direkt freigegeben werden.

Die `type_info::raw_name` Memberfunktion gibt ein `const char*` auf eine Null-terminierte Zeichenfolge, die den ergänzten Namen des Objekttyps darstellt. Der Name wird tatsächlich in seiner ergänzten Form gespeichert, um Platz zu sparen. Daher ist diese Funktion schneller als `type_info::name` , da es die namensergänzung nicht benötigt wird. Die zurückgegebene Zeichenfolge den `type_info::raw_name` Funktion eignet sich für Vergleichsvorgänge, aber ist nicht lesbar. Wenn Sie eine lesbare Zeichenfolge benötigen, verwenden Sie die `type_info::name` stattdessen funktionieren.

Typinformationen für polymorphe Klassen nur, wenn generiert die [/GR (Laufzeit-Typinformationen aktivieren)](../build/reference/gr-enable-run-time-type-information.md) -Compileroption angegeben ist.

## <a name="see-also"></a>Siehe auch

[Laufzeit-Typinformationen](../cpp/run-time-type-information.md)