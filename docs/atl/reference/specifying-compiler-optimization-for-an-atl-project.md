---
title: Angeben der Compileroptimierung für ein ATL-Projekt
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: c3b00823cb33be952451c3cc9e370c99140acc3c
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630612"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Angeben der Compileroptimierung für ein ATL-Projekt

Standardmäßig generiert der [ATL-Steuer](../../atl/reference/atl-control-wizard.md) Element-Assistent neue Klassen mit dem ATL_NO_VTABLE-Makro wie folgt:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL definiert dann _ATL_NO_VTABLE wie folgt:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

Wenn Sie _ATL_DISABLE_NO_VTABLE nicht definieren, wird das ATL_NO_VTABLE-Makro zu `declspec(novtable)`erweitert. Durch `declspec(novtable)`die Verwendung von in einer Klassen Deklaration wird verhindert, dass der vtable-Zeiger im Klassenkonstruktor und-Dekonstruktor initialisiert wird. Wenn Sie das Projekt erstellen, entfernt der Linker die Vtable und alle Funktionen, auf die die Vtable zeigt.

Sie müssen ATL_NO_VTABLE und folglich `declspec(novtable)`nur mit Basisklassen verwenden, die nicht direkt erstellbar sind. Sie dürfen nicht mit `declspec(novtable)` der am stärksten abgeleiteten Klasse in Ihrem Projekt verwenden, da diese Klasse (in der Regel [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md)oder [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) den vtable-Zeiger für das Projekt initialisiert.

Sie dürfen keine virtuellen Funktionen aus dem Konstruktor eines Objekts, das verwendet `declspec(novtable)`, abrufen. Sie sollten diese Aufrufe in die [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) -Methode verschieben.

Wenn Sie nicht sicher sind, ob Sie den `declspec(novtable)` -Modifizierer verwenden sollten, können Sie das ATL_NO_VTABLE-Makro aus einer beliebigen Klassendefinition entfernen, oder Sie können es durch Angeben von global deaktivieren.

```
#define _ATL_DISABLE_NO_VTABLE
```

in " *PCH. h* " (*stdafx. h* in Visual Studio 2017 und früher), bevor alle anderen ATL-Header Dateien eingeschlossen werden.

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)<br/>
[C++-Projektvorlagen](../../build/reference/visual-cpp-project-types.md)<br/>
[Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)
