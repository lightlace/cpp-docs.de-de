---
title: "IDL-Attribute, Eigenschaft Assistent zum Hinzufügen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec158c117161c5a5c2ffd23cef0d5c79c312ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idl-attributes-add-property-wizard"></a>IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften
Verwenden Sie diese Seite des Assistenten zum Hinzufügen einer Eigenschaft, um alle Interface Definition Language (IDL)-Einstellungen für die Eigenschaft anzugeben.  
  
 **ID**  
 Legt fest, die numerische ID, die die Eigenschaft identifiziert. Diese Option ist nicht für Eigenschaften von benutzerdefinierten Schnittstellen verfügbar. Finden Sie unter [Id](http://msdn.microsoft.com/library/windows/desktop/aa367040) in der *"MIDL" Referenz*.  
  
 **helpcontext**  
 Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu dieser Eigenschaft in der Hilfedatei. Finden Sie unter [Helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) in der *"MIDL" Referenz*.  
  
 **helpstring**  
 Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet. Standardmäßig wird es auf festgelegt "-Eigenschaft *Eigenschaftsname*." Finden Sie unter [Helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) in der *"MIDL" Referenz*.  
  
## <a name="other-options"></a>Weitere Optionen  
 Nicht alle Optionen sind für alle Eigenschaftentypen verfügbar.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**bindable**|Gibt an, dass die Eigenschaft die Datenbindung unterstützt. Finden Sie unter [bindbare](http://msdn.microsoft.com/library/windows/desktop/aa366738) in der *"MIDL" Referenz*. Für die vordefinierten Implementierung der Eigenschaft diese Option ist standardmäßig festgelegt und kann nicht geändert werden.|  
|**defaultbind**|Gibt an, dass dies die einfache, bindbare Eigenschaft bewährte darstellt das Objekt. Finden Sie unter [Defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) in der *"MIDL" Referenz*.|  
|**displaybind**|Gibt an, dass diese Eigenschaft für den Benutzer als bindbar angezeigt werden soll. Finden Sie unter [Displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) in der *"MIDL" Referenz*.|  
|**immediatebind**|Gibt an, dass die Datenbank sofort alle Änderungen an dieser Eigenschaft eines Objekts von datengebundenen benachrichtigt wird. Finden Sie unter [Immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) in der *"MIDL" Referenz*.|  
|**defaultcollelem**|Gibt an, dass die Eigenschaft eine Accessorfunktion für ein Element von der standardauflistung ist. Finden Sie unter [Defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) in der *"MIDL" Referenz*.|  
|**nonbrowsable**|Setzt einen Tag einer Schnittstelle oder Disp-Element, das nicht in einem Eigenschaftenbrowser angezeigt werden soll. Finden Sie unter [Nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) in der *"MIDL" Referenz*.|  
|**requestedit**|Gibt an, dass die Eigenschaft unterstützt die **OnRequestEdit** Benachrichtigung finden Sie unter [Requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) in der *"MIDL" Referenz*. Für die vordefinierten Implementierung der Eigenschaft diese Option ist standardmäßig festgelegt und kann nicht geändert werden.|  
|**Datenquelle**|Gibt an, dass ein Element der Eigenschaft eine Quelle von Ereignissen ist. Finden Sie unter [Quelle](http://msdn.microsoft.com/library/windows/desktop/aa367166) in der *"MIDL" Referenz*.|  
|**hidden**|Gibt an, dass die Eigenschaft vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll. Finden Sie unter [ausgeblendete](http://msdn.microsoft.com/library/windows/desktop/aa366861) in der *"MIDL" Referenz*.|  
|**restricted**|Gibt an, dass die Eigenschaft nach dem Zufallsprinzip aufgerufen werden kann. Finden Sie unter [eingeschränkte](http://msdn.microsoft.com/library/windows/desktop/aa367157) in der *"MIDL" Referenz*.|  
|`local`|Gibt die MIDL-Compiler, dass die Eigenschaft nicht remote ist. Finden Sie unter [lokale](http://msdn.microsoft.com/library/windows/desktop/aa367071) in der *"MIDL" Referenz*.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [Namen, hinzufügen Eigenschaft Assistent zum](../ide/names-add-property-wizard.md)   
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)   
 [Basiseigenschaften](../ide/stock-properties.md)