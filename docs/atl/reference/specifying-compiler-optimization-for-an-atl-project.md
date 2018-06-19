---
title: Angeben von Compileroptimierungen für ATL-Projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0060437613bcdd6281ce5cceb112f5fd7f470bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361969"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Angeben von Compileroptimierungen für ATL-Projekt
Wird standardmäßig die [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md) neue Klassen mit dem Makro ATL_NO_VTABLE folgendermaßen generiert:  
  
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
  
 Wenn Sie _ATL_DISABLE_NO_VTABLE nicht definieren, das ATL_NO_VTABLE-Makro wird erweitert, um `declspec(novtable)`. Mithilfe von `declspec(novtable)`in einer Klasse Deklaration verhindert, dass den Zeiger Vtable im Klassenkonstruktor und -Destruktor initialisiert wird. Wenn Sie das Projekt erstellen, entfällt der Linker Vtable sowie alle Funktionen, die auf denen Vtable zeigt.  
  
 Verwenden Sie ATL_NO_VTABLE und folglich `declspec(novtable)`, mit nur Basisklassen, die nicht direkt erstellbar sind. Verwenden Sie nicht `declspec(novtable)` mit der meisten abgeleiteten Klasse im Projekt, da diese Klasse (in der Regel [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), oder [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) Initialisiert den Vtable-Zeiger für das Projekt.  
  
 Virtuelle Funktionen dürfen nicht aufgerufen werden, aus dem Konstruktor der jedes Objekt, das verwendet `declspec(novtable)`. Sie sollten diese Aufrufe zum Verschieben der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) Methode.  

  
 Wenn Sie unsicher sind, ob Sie verwenden sollten die `declspec(novtable)` Modifizierer verwenden, können Sie das Makro ATL_NO_VTABLE aus einer beliebigen Klassendefinition entfernen, oder Sie können es global deaktivieren, indem Sie angeben  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 in "stdafx.h" sind, bevor Sie alle anderen ATL-Headerdateien enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

