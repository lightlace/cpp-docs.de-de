---
title: Klassen und Strukturen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: c28f83e7853ffb09bba7721ec71ab43c85aedb0c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779390"
---
# <a name="classes-and-structs-c"></a>Klassen und Strukturen (C++)

In diesem Abschnitt werden die C++-Klassen und -Strukturen vorgestellt. Die zwei Konstrukte sind identisch in C++. Der Unterschied besteht jedoch darin, dass der Standardzugriff in Strukturen öffentlich ist, während der Standard in Klassen privat ist.

Klassen und Strukturen sind die Konstrukte, anhand denen Sie Ihre eigenen Typen definieren. Klassen und Strukturen können Datenmember und Memberfunktionen enthalten. Mit diesen können Sie den Status und das Verhalten des Typs beschreiben.

Es sind folgende Themen enthalten:

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [Klassenmembers (Übersicht)](../cpp/class-member-overview.md)

- [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md)

- [Vererbung](../cpp/inheritance-cpp.md)

- [Statische Member](../cpp/static-members-cpp.md)

- [Benutzerdefinierte Typkonvertierungen](../cpp/user-defined-type-conversions-cpp.md)

- [Änderbare Datenmember (mutable Spezifizierer)](../cpp/mutable-data-members-cpp.md)

- [Geschachtelte Klassendeklarationen](../cpp/nested-class-declarations.md)

- [Anonyme Klassentypen](../cpp/anonymous-class-types.md)

- [Zeiger auf Member](../cpp/pointers-to-members.md)

- [this-Zeiger](../cpp/this-pointer.md)

- [C++-Bitfelder](../cpp/cpp-bit-fields.md)

Die drei Klassentypen sind "structure", "class" und "union". Sie deklariert werden, mithilfe der [Struktur](../cpp/struct-cpp.md), [Klasse](../cpp/class-cpp.md), und [Union](../cpp/unions.md) Schlüsselwörter. In der folgenden Tabelle werden die Unterschiede zwischen den drei Klassentypen gezeigt.

Weitere Informationen zu Unions finden Sie unter [Unions](../cpp/unions.md). Informationen über Klassen und Strukturen in C++ / CLI und C++ / CX, finden Sie unter [Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md).

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Zugriffssteuerung und Einschränkungen von Strukturen, Klassen und Unions

|Strukturen|Klassen|Unions|
|----------------|-------------|------------|
|Klassenschlüssel ist **Struktur**|Klassenschlüssel ist **Klasse**|Klassenschlüssel ist **Union**|
|Der Standardzugriff ist öffentlich.|Der Standardzugriff ist privat.|Der Standardzugriff ist öffentlich.|
|Keine Verwendungseinschränkungen|Keine Verwendungseinschränkungen|Verwenden Sie jeweils nur einen Member.|

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)