---
title: Bad_typeid-Ausnahme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cc93ab5a0f2d7fce12e926d571881ccb9c070fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092205"
---
# <a name="badtypeid-exception"></a>bad_typeid-Ausnahme

Die **Bad_typeid** Ausnahme wird von der [Typeid-Operator](../cpp/typeid-operator.md) bei der der Operand für **Typeid** ist ein Nullzeiger.

## <a name="syntax"></a>Syntax

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>Hinweise

Die Schnittstelle für **Bad_typeid** ist:

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();
};
```

Das folgende Beispiel zeigt die **Typeid** Operator Auslösen einer **Bad_typeid** Ausnahme.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>Ausgabe

```Output
Object is NULL
```

## <a name="see-also"></a>Siehe auch

[Laufzeit-Typinformationen](../cpp/run-time-type-information.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)