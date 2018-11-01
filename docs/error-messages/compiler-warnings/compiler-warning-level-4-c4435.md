---
title: Compilerwarnung (Stufe 4) C4435
ms.date: 11/04/2016
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 7db1d483f571289c5b890c223ba1e59ba3d1f41e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572327"
---
# <a name="compiler-warning-level-4-c4435"></a>Compilerwarnung (Stufe 4) C4435

'class1' : Das Objektlayout unter „/vd2“ wird aufgrund der virtuellen Basis 'class2' geändert.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Unter der standardmäßigen-Kompilierungsoption von/vd1, die abgeleitete Klasse verfügt nicht über eine `vtordisp` Feld für die angegebene virtuelle Basis.  Wenn "/ vd2" oder `#pragma vtordisp(2)` gültig ist, wird eine `vtordisp` Feld wird vorhanden ist, Ändern des Layouts des Objekts sein.  Dies kann zu Binärkompatibilität Problemen führen, wenn interagierenden Module mit unterschiedlichen kompiliert werden `vtordisp` Einstellungen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4435 generiert.

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