---
title: Compilerwarnung (Stufe 4) C4437
ms.date: 11/04/2016
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
ms.openlocfilehash: 9ff52ae6d10f7d4ba429bbf3457a2a6b969998d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037817"
---
# <a name="compiler-warning-level-4-c4437"></a>Compilerwarnung (Stufe 4) C4437

Dynamic_cast von virtueller Basis 'class1' zu 'Klasse2' konnte in bestimmten Kontexten Kompilieren mit "/ vd2" fehlschlagen oder 'Klasse2' mit #pragma vtordisp(2) wirksam zu definieren.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Der Compiler hat eine `dynamic_cast` Vorgang mit den folgenden Eigenschaften.

- Die Umwandlung ist von einem Zeiger Basisklasse in einer abgeleiteten Klasse Zeiger.

- Die abgeleitete Klasse erbt praktisch die Basisklasse.

- Die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die virtuelle Basisklasse.

- Die Umwandlung in einem Konstruktor oder Destruktor der abgeleiteten Klasse nicht gefunden wird, oder einige Klasse was erbt von der abgeleiteten Klasse (andernfalls compilerwarnung, die C4436 ausgegeben werden sollen).

Diese Warnung gibt an, die die `dynamic_cast` möglicherweise nicht richtig ausgeführt werden, wenn sie auf einem teilweise konstruierten Objekt ausgeführt wird.  Diese Situation tritt auf, wenn die einschließende Funktion in einem Konstruktor oder Destruktor einer Klasse, die die abgeleitete Klasse erbt, mit dem Namen in der Warnung aufgerufen wird.  Wenn die abgeleitete Klasse mit dem Namen in der Warnung nie Weitere wird abgeleitet werden soll, oder bei der objekterstellung oder Zerstörung der einschließende Funktion nicht aufgerufen wird, die Warnung kann ignoriert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel C4437 generiert und zeigt Code Generation entsteht das Problem, über die fehlende `vtordisp` Feld.

```cpp
// C4437.cpp
// To see the warning and runtime assert, compile with: /W4
// To eliminate the warning and assert, compile with: /W4 /vd2
//       or compile with: /W4 /DFIX
#pragma warning(default : 4437)
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
        func();
    }

    void func()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4437
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
[Compilerwarnung (Stufe 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)