---
title: "IDL-Attribute, Assistent zum Hinzuf&#252;gen von Eigenschaften"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.idlattributes"
dev_langs: 
  - "C++"
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# IDL-Attribute, Assistent zum Hinzuf&#252;gen von Eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Eigenschaften, um Einstellungen zur IDL \(Interface Definition Language\) für die Eigenschaft vorzunehmen.  
  
 **id**  
 Legt die numerische ID fest, durch die die Eigenschaft gekennzeichnet ist.  Diese Option ist für Eigenschaften von benutzerdefinierten Schnittstellen nicht verfügbar.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [id](http://msdn.microsoft.com/library/windows/desktop/aa367040).  
  
 **helpcontext**  
 Gibt eine Kontext\-ID an, über die der Benutzer Informationen zu dieser Eigenschaft in der Hilfedatei aufrufen kann.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851).  
  
 **helpstring**  
 Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.  Sie lautet standardmäßig "property *Eigenschaftenname*". Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856).  
  
## Weitere Optionen  
 Nicht alle Optionen sind für alle Eigenschaftentypen verfügbar.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**bindable**|Gibt an, dass die Eigenschaft Datenbindungen unterstützt.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738).  Bei der vordefinierten Implementierung der Eigenschaft wird diese Option standardmäßig festgelegt und kann nicht geändert werden.|  
|**defaultbind**|Gibt an, dass diese einzelne **bindable**\-Eigenschaft das Objekt am besten darstellt.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790).|  
|**displaybind**|Gibt an, dass diese Eigenschaft dem Benutzer als **bindable**\-Eigenschaft angezeigt werden sollte.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804).|  
|**immediatebind**|Gibt an, dass die Datenbank umgehend über alle Änderungen an dieser Eigenschaft eines datengebundenen Objekts benachrichtigt wird.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045).|  
|**defaultcollelem**|Gibt an, dass die Eigenschaft eine Accessorfunktion für ein Element der Standardauflistung ist.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792).|  
|**nonbrowsable**|Kennzeichnet ein Schnittstellen\- oder Dispatchschnittstellen\-Element, das in einem Eigenschaftenbrowser nicht angezeigt werden sollte.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117).|  
|**requestedit**|Gibt an, dass die Eigenschaft die **OnRequestEdit**\-Benachrichtigung unterstützt. Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155).  Bei der vordefinierten Implementierung der Eigenschaft wird diese Option standardmäßig festgelegt und kann nicht geändert werden.|  
|**source**|Gibt an, dass ein Element der Eigenschaft eine Ereignisquelle ist.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [source](http://msdn.microsoft.com/library/windows/desktop/aa367166).|  
|**hidden**|Gibt an, dass die Eigenschaft vorhanden ist, in einem benutzerorientierten Browser jedoch nicht angezeigt werden sollte.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861).|  
|**restricted**|Gibt an, dass die Eigenschaft nicht willkürlich aufgerufen werden kann.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157).|  
|`local`|Signalisiert dem MIDL\-Compiler, dass es sich nicht um eine Remoteeigenschaft handelt.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [local](http://msdn.microsoft.com/library/windows/desktop/aa367071).|  
  
## Siehe auch  
 [Hinzufügen einer Eigenschaft](../ide/adding-a-property-visual-cpp.md)   
 [Namen, Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md)   
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)   
 [Basiseigenschaften](../ide/stock-properties.md)