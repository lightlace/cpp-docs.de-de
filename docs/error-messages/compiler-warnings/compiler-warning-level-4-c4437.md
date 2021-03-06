---
title: Compilerwarnung (Stufe 4) C4437
ms.date: 11/04/2016
f1_keywords:
- C4437
helpviewer_keywords:
- C4437
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
ms.openlocfilehash: 6cd50d5c4d79b82c135ab4e84ec390dee9e906ef
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810654"
---
# <a name="compiler-warning-level-4-c4437"></a>Compilerwarnung (Stufe 4) C4437

die dynamic_cast von der virtuellen Basis "Class1" zu "Klasse2" kann in einigen Kontexten fehlschlagen, die mit "/vd2" kompiliert werden, oder "Klasse2" mit #Pragma vtordisp (2) definieren.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Der Compiler hat einen `dynamic_cast` Vorgang mit den folgenden Merkmalen gefunden.

- Die Umwandlung erfolgt von einem Basisklassen Zeiger auf einen abgeleiteten Klassen Zeiger.

- Die abgeleitete Klasse erbt virtuell die Basisklasse.

- Die abgeleitete Klasse verfügt über kein `vtordisp` Feld für die virtuelle Basis.

- Die Umwandlung wurde nicht in einem Konstruktor oder Dekonstruktor der abgeleiteten Klasse gefunden, oder eine Klasse, die weiter von der abgeleiteten Klasse erbt (andernfalls wird die Compilerwarnung C4436 ausgegeben).

Die Warnung gibt an, dass die `dynamic_cast` möglicherweise nicht ordnungsgemäß ausgeführt wird, wenn Sie auf einem teilweise konstruierten Objekt ausgeführt wird.  Diese Situation tritt auf, wenn die einschließende Funktion von einem Konstruktor oder Dekonstruktor einer Klasse aufgerufen wird, die die abgeleitete Klasse erbt, die in der Warnung benannt ist.  Wenn die abgeleitete Klasse, die in der Warnung benannt ist, nie weiter abgeleitet wird oder die einschließende Funktion nicht während der Objekt Erstellung oder-Zerstörung aufgerufen wird, kann die Warnung ignoriert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4437 generiert und das Code Generierungs Problem veranschaulicht, das sich aus dem Feld Missing `vtordisp` ergibt.

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
[Compilerwarnung (Ebene 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)