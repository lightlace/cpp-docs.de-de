---
title: Primäre Ausdrücke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee1ca97004d6dddb1e98ada14f06305f782b674a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092246"
---
# <a name="primary-expressions"></a>Primäre Ausdrücke

Primäre Ausdrücke sind die Bausteine für komplexere Ausdrücke. Es handelt sich um Literale, Namen und Namen, die vom Bereichsauflösungsoperator (`::`) qualifiziert werden.  Ein primärer Ausdruck kann jede der folgenden Formen haben:

```
literal
this
name
::name ( expression )
```

Ein *literal* ist ein konstanter primärer Ausdruck. Sein Typ hängt von der Form seiner Spezifikation ab. Finden Sie unter [Literale](../cpp/numeric-boolean-and-pointer-literals-cpp.md) vollständige Informationen zum Festlegen von Literalen.

Die **dies** -Schlüsselwort ist ein Zeiger auf ein Objekt der Klasse. Es ist innerhalb von nicht statische Memberfunktionen verfügbar und zeigt auf die Instanz der Klasse, für die die Funktion aufgerufen wurde. Die **dies** Schlüsselwort kann nicht außerhalb des Texts einer Klasse eine Memberfunktion verwendet werden.

Der Typ des der **dies** -Zeiger ist `type`  **\*const** (, in denen `type` ist der Klassenname) innerhalb von Funktionen, die nicht speziell Ändern der **dieser** Zeiger. Das folgende Beispiel zeigt Member Funktionsdeklarationen und die Typen von **dies**:

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

Finden Sie unter [this-Zeigers](this-pointer.md) für Weitere Informationen zum Ändern des Typs der **dies** Zeiger.

Der Bereichsauflösungsoperator (`::`) gefolgt von einem Namen stellt einen primären Ausdruck dar.  Solche Namen müssen Namen von globaler Reichweite sein, nicht Membernamen.  Der Typ dieses Ausdrucks wird durch die Deklaration des Namens bestimmt. Es ist ein l-Wert (das heißt, er kann auf der linken Seite eines Zuweisungsoperatorausdrucks angezeigt werden), wenn der deklarierende Name ein l-Wert ist. Der Bereichsauflösungsoperator lässt zu, dass auf einen globalen Namen verwiesen wird, selbst wenn dieser Name im aktuellen Bereich ausgeblendet ist. Finden Sie unter [Bereich](../cpp/scope-visual-cpp.md) für verdeutlicht, wie Sie mit dem Bereichsauflösungsoperator.

Ein in Klammern eingefasster Ausdruck ist ein primärer Ausdruck, dessen Typ und Wert mit denen des nicht in Klammern stehenden Ausdrucks identisch sind. Es ist ein l-Wert, wenn der nicht in Klammern stehende Ausdruck ein l-Wert ist.

Zu den Beispielen von primären Ausdrücken gehören:

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

Die folgenden Beispiele gelten als *Namen*, und daher sind Sie primäre Ausdrücke in verschiedenen Formen:

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>Siehe auch

[Ausdruckstypen](../cpp/types-of-expressions.md)