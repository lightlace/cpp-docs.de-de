---
title: Typeid-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db9e019c3c9cc7e7e71726a8bd11e83ca4c99cdf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020663"
---
# <a name="typeid-operator"></a>typeid-Operator

## <a name="syntax"></a>Syntax

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Hinweise

Die **Typeid** Operator ermöglicht, den Typ eines Objekts zur Laufzeit bestimmt werden.

Das Ergebnis des **Typeid** ist eine `const type_info&`. Der Wert ist ein Verweis auf eine `type_info` Objekt, das entweder darstellt der *Typ-Id* oder den Typ des der *Ausdruck*, je nachdem, für welche Form der **Typeid** wird verwendet. Finden Sie unter [Type_info-Klasse](../cpp/type-info-class.md) für Weitere Informationen.

Die **Typeid** Operator funktioniert nicht mit verwalteten Typen (abstrakten Deklaratoren oder Instanzen), finden Sie unter [Typeid](../windows/typeid-cpp-component-extensions.md) Informationen zum Abrufen der <xref:System.Type> eines angegebenen Typs.

Die **Typeid** Operator wird eine laufzeitüberprüfung aus, wenn auf ein l-Wert eines polymorphen Klassentyps angewendet, in dem der tatsächliche Typ des Objekts kann nicht von der statischen Informationen bestimmt werden. Zu solchen Fällen zählen folgende:

- Ein Verweis auf eine Klasse

- Ein Zeiger ist, mit dereferenziert \*

- Ein indizierter Zeiger (d. h. [ ]). (Beachten Sie, dass es im Allgemeinen nicht sicher ist, einen Index mit einem Zeiger auf einen polymorphen Typ zu verwenden.)

Wenn die *Ausdruck* auf einen Basisklassentyp verweist, aber das Objekt tatsächlich ein von dieser Basisklasse abgeleiteter Typ ist ein `type_info` Verweis auf die abgeleitete Klasse das Ergebnis ist. Die *Ausdruck* muss auf einen polymorphen Typ (eine Klasse mit virtuellen Funktionen) verweisen. Das Ergebnis, andernfalls ist der `type_info` für die statische Klasse, die gemäß der *Ausdruck*. Darüber hinaus muss der Zeiger dereferenziert werden, sodass das Objekt, auf das er zeigt, verwendet wird. Ohne Dereferenzierung des Zeigers ist das Ergebnis wird die `type_info` für den Zeiger, der nicht dessen Ziel auf. Zum Beispiel:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo.h>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

Wenn die *Ausdruck* wird einen Zeiger dereferenziert und der Zeigerwert 0 (null), ist **Typeid** löst eine [Bad_typeid-Ausnahme](../cpp/bad-typeid-exception.md). Wenn der Zeiger nicht auf ein gültiges Objekt verweist eine `__non_rtti_object` Ausnahme ausgelöst wird, wird, der angibt, auf die RTTI zu analysieren, die einen Fehler ausgelöst hat (z.B. zugriffsverletzungen), da das Objekt aus irgendeinem Grund ungültig ist (ungültiger Zeiger oder der Code wurde nicht kompiliert mit [/Gr](../build/reference/gr-enable-run-time-type-information.md)).

Wenn die *Ausdruck* ist weder ein Zeiger noch ein Verweis auf eine Basisklasse des Objekts, das Ergebnis ist eine `type_info` Verweis, der den statischen Typ des darstellt der *Ausdruck*. Die *statischen Typ* eines Ausdrucks verweist auf den Typ eines Ausdrucks, wie zum Zeitpunkt der Kompilierung bekannt ist. Die Ausführungssemantik wird ignoriert, wenn der statische Typ eines Ausdrucks bewertet wird. Außerdem werden wenn möglich Verweise ignoriert, wenn der statische Typ eines Ausdrucks bestimmt wird:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**Typeid** kann auch in den Vorlagen um den Typ eines Vorlagenparameters zu bestimmen, verwendet werden:

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>Siehe auch

[Laufzeit-Typinformationen](../cpp/run-time-type-information.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)