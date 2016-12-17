---
title: "Festlegen der Compileroptimierung f&#252;r ein ATL-Projekt"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.optimization"
  - "vc.appwiz.ATL.vtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Compileroptimierung"
  - "ATL_DISABLE_NO_VTABLE-Makro"
  - "ATL_NO_VTABLE-Makro"
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Festlegen der Compileroptimierung f&#252;r ein ATL-Projekt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der [ATL\-Steuerelement\-Assistent](../../atl/reference/atl-control-wizard.md) erstellt standardmäßig neue Klassen mit dem **ATL\_NO\_VTABLE**\-Makro. Beispiel:  
  
```  
class ATL_NO_VTABLE CProjName  
{  
   ...  
};  
```  
  
 **\_ATL\_NO\_VTABLE** wird von ATL anschließend wie folgt definiert:  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
   #define ATL_NO_VTABLE  
#else  
   #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 Wenn Sie **\_ATL\_DISABLE\_NO\_VTABLE** nicht definieren, wird das **ATL\_NO\_VTABLE**\-Makro zu `declspec(novtable)` erweitert.  Durch die Verwendung von `declspec(novtable)`in einer Klassendeklaration wird verhindert, dass der **vtable**\-Zeiger im Klassenkonstruktor und \-destruktor initialisiert wird.  Wenn Sie das Projekt erstellen, werden **vtable** und sämtliche Funktionen, auf die von **vtable** verwiesen wird, vom Linker entfernt.  
  
 **ATL\_NO\_VTABLE** und folglich auch `declspec(novtable)` dürfen nur mit Basisklassen verwendet werden, die nicht direkt erstellbar sind.  `declspec(novtable)` darf nicht mit der am meisten abgeleiteten Klasse im Projekt verwendet werden, da diese Klasse \(normalerweise [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md) oder [CComPolyObject](../../atl/reference/ccompolyobject-class.md)\) den **vtable**\-Zeiger für das Projekt initialisiert.  
  
 Virtuelle Funktionen dürfen nicht vom Konstruktor eines Objekts aufgerufen werden, das `declspec(novtable)` verwendet.  Sie sollten diese Aufrufe in die [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)\-Methode verschieben.  
  
 Wenn Sie nicht sicher sind, ob Sie den `declspec(novtable)`\-Modifizierer verwenden sollten, können Sie das **ATL\_NO\_VTABLE**\-Makro aus einer beliebigen Klassendefinition entfernen oder es global durch die Codezeichenfolge  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 in **stdafx.h** deaktivieren, bevor alle anderen ATL\-Headerdateien einbezogen werden.  
  
## Siehe auch  
 [ATL\-Projekt\-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+\-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL\- und C\-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Standardmäßige ATL\-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)