---
title: Festlegen der Compileroptimierung für ein ATL-Projekt
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: 812245133b4b3b870c0c763eabcda0ec8d26e028
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221047"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Festlegen der Compileroptimierung für ein ATL-Projekt

In der Standardeinstellung die [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md) neue Klassen mit dem Makro ATL_NO_VTABLE wie folgt generiert:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL definiert _ATL_NO_VTABLE wie folgt:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

Wenn Sie keine _ATL_DISABLE_NO_VTABLE definieren, das ATL_NO_VTABLE-Makro erweitert wird, um `declspec(novtable)`. Mithilfe von `declspec(novtable)`in einer Klasse Deklaration wird verhindert, dass den Vtable-Zeiger im Klassenkonstruktor und Destruktor initialisiert wird. Wenn Sie Ihr Projekt erstellen, entfällt der Linker die Vtable und alle Funktionen, die auf denen die Vtable verweist.

Verwenden Sie ATL_NO_VTABLE, und folglich `declspec(novtable)`, nur mit Basisklassen, die nicht direkt erstellbar sind. Verwenden Sie nicht `declspec(novtable)` mit der am stärksten abgeleiteten Klasse in Ihrem Projekt, da diese Klasse (in der Regel [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), oder [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) Initialisiert den Vtable-Zeiger für das Projekt an.

Sie müssen nicht virtuelle Funktionen aufrufen, aus dem Konstruktor eines Objekts, das verwendet `declspec(novtable)`. Sie sollten diese Aufrufe zum Verschieben der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) Methode.

Wenn Sie nicht sicher sind, ob Sie verwenden, sollten die `declspec(novtable)` Modifizierer verwenden, können Sie das Makro ATL_NO_VTABLE aus einer beliebigen Klassendefinition entfernen oder Sie können es global deaktivieren, indem Sie angeben

```
#define _ATL_DISABLE_NO_VTABLE
```

in der Datei stdafx.h sind, bevor alle anderen ATL-Headerdateien enthalten.

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)<br/>
[C++Projekttypen in Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)
