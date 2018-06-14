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
ms.openlocfilehash: 77931296d8d33337c4e630b7327a1ec8fd0a458f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340189"
---
# <a name="idl-attributes-add-property-wizard"></a>IDL-Attribute, Assistent zum Hinzufügen von Eigenschaften
Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Eigenschaften, um IDL-Einstellungen (Interface Definiton Language) für die Eigenschaft anzugeben.  
  
 **ID**  
 Legt die numerische ID fest, die die Eigenschaft identifiziert. Diese Option ist nicht für Eigenschaften von benutzerdefinierten Schnittstellen verfügbar. Informationen finden Sie in der *MIDL-Referenz* unter [id](http://msdn.microsoft.com/library/windows/desktop/aa367040).  
  
 **helpcontext**  
 Gibt eine Kontext-ID an, die das Anzeigen von Informationen über diese Eigenschaft in der Hilfedatei ermöglicht. Informationen finden Sie in der *MIDL-Referenz* unter [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851).  
  
 **helpstring**  
 Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird. Wird standardmäßig auf „property *Eigenschaftenname*“ festgelegt. Informationen finden Sie in der *MIDL-Referenz* unter [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856).  
  
## <a name="other-options"></a>Weitere Optionen  
 Nicht alle Optionen sind für alle Eigenschaftentypen verfügbar.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**bindable**|Gibt an, dass die Eigenschaft die Datenbindung unterstützt. Informationen finden Sie in der *MIDL-Referenz* unter [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738). Diese Option ist standardmäßig für die vordefinierte Implementierung der Eigenschaft festgelegt und kann nicht geändert werden.|  
|**defaultbind**|Gibt an, dass diese einzelne bindbare Eigenschaft das Objekt am besten darstellt. Informationen finden Sie in der *MIDL-Referenz* unter [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790).|  
|**displaybind**|Gibt an, dass diese Eigenschaft für den Benutzer als bindbar angezeigt werden soll. Informationen finden Sie in der *MIDL-Referenz* unter [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804).|  
|**immediatebind**|Gibt an, dass die Datenbank umgehend von allen an dieser Eigenschaft eines datengebundenen Objekts vorgenommenen Änderungen benachrichtigt wird. Informationen finden Sie in der *MIDL-Referenz* unter [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045).|  
|**defaultcollelem**|Gibt an, dass die Eigenschaft eine Accessorfunktion für ein Element der Standardsammlung ist. Informationen finden Sie in der *MIDL-Referenz* unter [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792).|  
|**nonbrowsable**|Markiert ein Member einer Schnittstelle oder Disp-Schnittstelle, der nicht in einem Eigenschaftenbrowser angezeigt werden soll. Informationen finden Sie in der *MIDL-Referenz* unter [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117).|  
|**requestedit**|Gibt an, dass die Eigenschaft die **OnRequestEdit**-Benachrichtigung unterstützt. Informationen finden Sie in der *MIDL-Referenz* unter [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155). Diese Option ist standardmäßig für die vordefinierte Implementierung der Eigenschaft festgelegt und kann nicht geändert werden.|  
|**source**|Gibt an, dass ein Member dieser Eigenschaft eine Ereignisquelle ist. Informationen finden Sie in der *MIDL-Referenz* unter [source](http://msdn.microsoft.com/library/windows/desktop/aa367166).|  
|**hidden**|Gibt an, dass die Eigenschaft vorhanden ist, aber nicht in einem benutzerorientierten Browser angezeigt werden sollte. Informationen finden Sie in der *MIDL-Referenz* unter [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861).|  
|**restricted**|Gibt an, dass die Eigenschaft nicht beliebig aufgerufen werden kann. Informationen finden Sie in der *MIDL-Referenz* unter [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157).|  
|`local`|Gibt für den MIDL-Compiler an, dass die Eigenschaft lokal ist. Informationen finden Sie in der *MIDL-Referenz* unter [local](http://msdn.microsoft.com/library/windows/desktop/aa367071).|  
  
## <a name="see-also"></a>Siehe auch  
 [Adding a Property (Hinzufügen einer Eigenschaft)](../ide/adding-a-property-visual-cpp.md)   
 [Names, Add Property Wizard (Namen, Assistent zum Hinzufügen von Eigenschaften)](../ide/names-add-property-wizard.md)   
 [Implementing an Interface (Implementieren einer Schnittstelle)](../ide/implementing-an-interface-visual-cpp.md)   
 [Basiseigenschaften](../ide/stock-properties.md)