---
title: Compilerwarnung (Stufe 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 0ff545d3de3ef173cdbfd99d7714890e8631ce7a
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810662"
---
# <a name="compiler-warning-level-4-c4435"></a>Compilerwarnung (Stufe 4) C4435

'class1' : Das Objektlayout unter „/vd2“ wird aufgrund der virtuellen Basis 'class2' geändert.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Unter der standardmäßigen Kompilierungs Option von/VD1-hat die abgeleitete Klasse kein `vtordisp` Feld für die virtuelle Basis.  Wenn "/vd2" oder `#pragma vtordisp(2)` wirksam ist, wird ein `vtordisp` Feld vorhanden sein, das das Objekt Layout ändert.  Dies kann zu binären Kompatibilitätsproblemen führen, wenn interagierende Module mit unterschiedlichen `vtordisp` Einstellungen kompiliert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4435 generiert.

```cpp
// C4435.cpp
// compile with: /c /W4
#pragma warning(default : 4435)
class A
{
public:
    virtual ~A() {}
};

class B : public virtual A  // C4435
{};
```

## <a name="see-also"></a>Siehe auch

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/vd (Konstruktionsverschiebungen deaktivieren)](../../build/reference/vd-disable-construction-displacements.md)