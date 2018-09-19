---
title: Compilerwarnung (Stufe 1) C4436 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2484b5420347f49a74d8eb3cdf65a8221741cc63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076501"
---
# <a name="compiler-warning-level-1-c4436"></a>Compilerwarnung (Stufe 1) C4436

Dynamic_cast von virtueller Basis 'class1' zu 'Klasse2' im Konstruktor oder Destruktor könnte 'Klasse2' mit #pragma vtordisp(2) wirksam definieren oder beim teilweise konstruierten Objekt Kompilieren mit "/ vd2" auftreten

Der Compiler hat eine `dynamic_cast` Vorgang mit den folgenden Eigenschaften.

- Die Umwandlung ist von einem Zeiger Basisklasse in einer abgeleiteten Klasse Zeiger.

- Die abgeleitete Klasse erbt praktisch die Basisklasse.

- Die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die virtuelle Basisklasse.

- Die Umwandlung in einen Konstruktor oder Destruktor der abgeleiteten Klasse gefunden wird, oder eine Klasse, was von der abgeleiteten Klasse erbt.

Diese Warnung gibt an die `dynamic_cast` möglicherweise nicht ordnungsgemäß ausgeführt werden, wenn sie auf einem teilweise konstruierten Objekt ausgeführt wird.  Das geschieht, wenn der abgeleitete Konstruktor/Destruktor auf einem untergeordneten Objekt des einige weitere abgeleitete Objekt ausgeführt wird.  Wenn die abgeleitete Klasse, die mit dem Namen in der Warnung nie Weitere wird abgeleitet, die ignoriert werden kann.

## <a name="example"></a>Beispiel

Im folgenden Beispiel C4436 generiert und zeigt Code Generation entsteht das Problem, über die fehlende `vtordisp` Feld.

```cpp
// C4436.cpp
// To see the warning and runtime assert, compile with: /W1
// To eliminate the warning and assert, compile with: /W1 /vd2
//       or compile with: /W1 /DFIX
#include <cassert>

struct A
{
public:
    virtual ~A() {}
};

#if defined(FIX)
#pragma vtordisp(push, 2)
#endif
struct B : virtual A
{
    B()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4436
        assert(this == b);              // assert unless compiled with /vd2
    }
};
#if defined(FIX)
#pragma vtordisp(pop)
#endif

struct C : B
{
    int i;
};

int main()
{
    C c;
}
```

## <a name="see-also"></a>Siehe auch

[dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Compilerwarnung (Ebene 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)