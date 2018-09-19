---
title: Bad_cast-Ausnahme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bd5bb63e075303856d444cb08c2c1f3abe990b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083937"
---
# <a name="badcast-exception"></a>bad_cast-Ausnahme

Die **Bad_cast** Ausnahme wird von der **Dynamic_cast** -Operator als Folge eines fehlerhaften Umwandlung in einen Verweistyp handelt.

## <a name="syntax"></a>Syntax

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Hinweise

Die Schnittstelle für **Bad_cast** ist:

```cpp
class bad_cast : public exception {
public:
   bad_cast(const char * _Message = "bad cast");
   bad_cast(const bad_cast &);
   virtual ~bad_cast();
};
```

Der folgende Code enthält ein Beispiel für eine fehlerhafte **Dynamic_cast** auslöst, die die **Bad_cast** Ausnahme.

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
#include <iostream>

class Shape {
public:
   virtual void virtualfunc() const {}
};

class Circle: public Shape {
public:
   virtual void virtualfunc() const {}
};

using namespace std;
int main() {
   Shape shape_instance;
   Shape& ref_shape = shape_instance;
   try {
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);
   }
   catch (bad_cast b) {
      cout << "Caught: " << b.what();
   }
}
```

Die Ausnahme wird ausgelöst, weil das umgewandelte Objekt (eine Form) nicht vom angegebenen Umwandlungstyp (Kreis) abgeleitet wird. Um die Ausnahme zu vermeiden, fügen Sie `main` diese Deklarationen hinzu:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Kehren Sie dann den Sinn der Umwandlung in den **versuchen** -Block wie folgt:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="see-also"></a>Siehe auch

[dynamic_cast-Operator](../cpp/dynamic-cast-operator.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)