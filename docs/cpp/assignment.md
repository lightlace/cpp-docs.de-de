---
title: Zuweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05f88eaaef32c509b400441830b5dcc311bf6769
ms.sourcegitcommit: 7127467af82147657d0fd7a41fe9c633c4a8453c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43054014"
---
# <a name="assignment"></a>Zuweisung

Der Zuweisungsoperator (**=**) ist strenggenommen ein binärer Operator. Seine Deklaration ist mit jedem anderen binären Operator identisch, mit den folgenden Ausnahmen:

- Es muss eine nicht statische Memberfunktion sein. Keine **Operator =** kann als nichtmemberfunktion deklariert werden.
- Es wird nicht von abgeleiteten Klassen geerbt.
- Eine standardmäßige **Operator =** Funktion kann vom Compiler für Klassentypen generiert werden, wenn keiner vorhanden ist.

Das folgende Beispiel veranschaulicht, wie Sie einen Zuweisungsoperator deklarieren:

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

Das angegebene Argument ist der rechten Seite des Ausdrucks. Der Operator gibt das Objekt zurück, um das Verhalten des Zuweisungsoperators beizubehalten, der den Wert des linken Rands zurückgibt, nachdem die Zuweisung abgeschlossen ist. Dies ermöglicht das Verketten von Zuweisungen, wie z. B.:

```cpp
pt1 = pt2 = pt3;
```

Der Kopierzuweisungsoperator ist nicht zu verwechseln mit der Copy-Konstruktor. Letztere wird während der Erstellung eines neuen Objekts aus einer vorhandenen aufgerufen:

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is line is similar to the following:
Point pt4(pt1); // Copy constructor call
```

> [!NOTE]
> Es wird empfohlen, führen die [Regel 3](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) , dass eine Klasse, die einen Kopierzuweisungsoperator definiert auch explizit Kopierkonstruktor definieren muss, Destruktor und, beginnend mit C ++ 11-verschiebezuweisung Konstruktors und verschieben Sie Operator.

## <a name="see-also"></a>Siehe auch

- [Operatorüberladung](../cpp/operator-overloading.md)
- [Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)