---
title: "Angeben von Compileroptimierungen für ein ATL-Projekt | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: abdad4367e75c1971ba5d11af1a60992d1bb3dd4
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Angeben von Compileroptimierungen für ein ATL-Projekt
In der Standardeinstellung die [ATL-Steuerelement-Assistent](../../atl/reference/atl-control-wizard.md) neue Klassen mit dem Makro ATL_NO_VTABLE folgendermaßen generiert:  
  
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
  
 Wenn Sie _ATL_DISABLE_NO_VTABLE nicht definieren, erweitert das ATL_NO_VTABLE-Makro zu `declspec(novtable)`. Mithilfe von `declspec(novtable)`in einer Klasse Deklaration verhindert, dass den Vtable-Zeiger im Klassenkonstruktor und -Destruktor initialisiert wird. Wenn Sie das Projekt erstellen, entfällt der Linker Vtable und alle Funktionen, die auf die Vtable verwiesen.  
  
 Verwenden Sie ATL_NO_VTABLE und folglich `declspec(novtable)`, nur mit Basisklassen, die nicht direkt erstellbar sind. Verwenden Sie nicht `declspec(novtable)` mit der am meisten abgeleiteten Klasse im Projekt, da diese Klasse (normalerweise [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), oder [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) initialisiert den Vtable-Zeiger für das Projekt.  
  
 Virtuelle Funktionen dürfen nicht vom Konstruktor eines Objekts, das verwendet aufgerufen `declspec(novtable)`. Sie sollten diese Aufrufe zum Verschieben der [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) Methode.  

  
 Wenn Sie nicht sicher sind, ob Sie verwenden sollten die `declspec(novtable)` Modifizierer verwenden, können Sie das ATL_NO_VTABLE-Makro aus einer beliebigen Klassendefinition entfernen oder Sie können es global deaktivieren, indem Sie angeben  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 in der Datei stdafx.h sind, bevor alle anderen ATL-Headerdateien enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)


