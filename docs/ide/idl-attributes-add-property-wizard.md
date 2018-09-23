---
title: IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7da654321dfae520f458374654a21a9e8ebb98f5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706649"
---
# <a name="idl-attributes-add-property-wizard"></a>IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften
Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Eigenschaften, um IDL-Einstellungen (Interface Definiton Language) für die Eigenschaft anzugeben.  
  
- **ID**

   Legt die numerische ID fest, die die Eigenschaft identifiziert. Diese Option ist nicht für Eigenschaften von benutzerdefinierten Schnittstellen verfügbar. Informationen finden Sie in der *MIDL-Referenz* unter [id](/windows/desktop/Midl/id).  
  
- **helpcontext**

   Gibt eine Kontext-ID an, die das Anzeigen von Informationen über diese Eigenschaft in der Hilfedatei ermöglicht. Informationen finden Sie in der *MIDL-Referenz* unter [helpcontext](/windows/desktop/Midl/helpcontext).  
  
- **helpstring**

   Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird. Wird standardmäßig auf „property *Eigenschaftenname*“ festgelegt. Informationen finden Sie in der *MIDL-Referenz* unter [helpstring](/windows/desktop/Midl/helpstring).  
  
## <a name="other-options"></a>Weitere Optionen  

Nicht alle Optionen sind für alle Eigenschaftentypen verfügbar.  
  
|Option|Beschreibung |  
|------------|-----------------|  
|**bindable**|Gibt an, dass die Eigenschaft die Datenbindung unterstützt. Informationen finden Sie in der *MIDL-Referenz* unter [bindable](/windows/desktop/Midl/bindable). Diese Option ist standardmäßig für die vordefinierte Implementierung der Eigenschaft festgelegt und kann nicht geändert werden.|  
|**defaultbind**|Gibt an, dass diese einzelne bindbare Eigenschaft das Objekt am besten darstellt. Informationen finden Sie in der *MIDL-Referenz* unter [defaultbind](/windows/desktop/Midl/defaultbind).|  
|**displaybind**|Gibt an, dass diese Eigenschaft für den Benutzer als bindbar angezeigt werden soll. Informationen finden Sie in der *MIDL-Referenz* unter [displaybind](/windows/desktop/Midl/displaybind).|  
|**immediatebind**|Gibt an, dass die Datenbank umgehend von allen an dieser Eigenschaft eines datengebundenen Objekts vorgenommenen Änderungen benachrichtigt wird. Informationen finden Sie in der *MIDL-Referenz* unter [immediatebind](/windows/desktop/Midl/immediatebind).|  
|**defaultcollelem**|Gibt an, dass die Eigenschaft eine Accessorfunktion für ein Element der Standardsammlung ist. Informationen finden Sie in der *MIDL-Referenz* unter [defaultcollelem](/windows/desktop/Midl/defaultcollelem).|  
|**nonbrowsable**|Markiert ein Member einer Schnittstelle oder Disp-Schnittstelle, der nicht in einem Eigenschaftenbrowser angezeigt werden soll. Informationen finden Sie in der *MIDL-Referenz* unter [nonbrowsable](/windows/desktop/Midl/nonbrowsable).|  
|**requestedit**|Gibt an, dass die Eigenschaft die **OnRequestEdit**-Benachrichtigung unterstützt. Informationen finden Sie in der *MIDL-Referenz* unter [requestedit](/windows/desktop/Midl/requestedit). Diese Option ist standardmäßig für die vordefinierte Implementierung der Eigenschaft festgelegt und kann nicht geändert werden.|  
|**source**|Gibt an, dass ein Member dieser Eigenschaft eine Ereignisquelle ist. Informationen finden Sie in der *MIDL-Referenz* unter [source](/windows/desktop/Midl/source).|  
|**hidden**|Gibt an, dass die Eigenschaft vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden sollte. Informationen finden Sie in der *MIDL-Referenz* unter [hidden](/windows/desktop/Midl/hidden).|  
|**restricted**|Gibt an, dass die Eigenschaft nicht beliebig aufgerufen werden kann. Informationen finden Sie in der *MIDL-Referenz* unter [restricted](/windows/desktop/Midl/restricted).|  
|`local`|Gibt für den MIDL-Compiler an, dass die Eigenschaft lokal ist. Informationen finden Sie in der *MIDL-Referenz* unter [local](/windows/desktop/Midl/local).|  
  
## <a name="see-also"></a>Siehe auch  
 [Adding a Property (Hinzufügen einer Eigenschaft)](../ide/adding-a-property-visual-cpp.md)   
 [Names, Add Property Wizard (Namen, Assistent zum Hinzufügen von Eigenschaften)](../ide/names-add-property-wizard.md)   
 [Implementing an Interface (Implementieren einer Schnittstelle)](../ide/implementing-an-interface-visual-cpp.md)   
 [Basiseigenschaften](../ide/stock-properties.md)