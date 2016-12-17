---
title: "IDL-Attribute, Assistent zum Hinzuf&#252;gen von Methoden"
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
  - "vc.codewiz.method.idlattrib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Hinzufügen von Methoden [C++]"
  - "IDL-Attribute, Assistent zum Hinzufügen von Methoden"
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# IDL-Attribute, Assistent zum Hinzuf&#252;gen von Methoden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten zum Hinzufügen von Methoden, um für die Methode alle Einstellungen zur IDL \(Interface Definition Language\) festzulegen.  
  
 **id**  
 Legt die numerische ID zur Kennzeichnung der Methode fest.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [id](http://msdn.microsoft.com/library/windows/desktop/aa367040).  
  
 Dieses Feld ist für benutzerdefinierte Schnittstellen sowie für MFC\-Dispatchschnittstellen nicht verfügbar.  
  
 **call\_as**  
 Gibt den Namen einer Remotemethode an, der diese lokale Methode zugeordnet werden kann.  Weitere Informationen finden Sie in der *MIDL\-Referenz* unter [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748).  
  
 Für MFC\-Dispatchschnittstellen nicht verfügbar.  
  
 **helpcontext**  
 Gibt eine Kontext\-ID an, über die der Benutzer Informationen zur entsprechenden Methode in der Hilfedatei anzeigen kann.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851).  
  
 Für MFC\-Dispatchschnittstellen nicht verfügbar.  
  
 **helpstring**  
 Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.  Standardmäßig lautet sie "Methode *Methodenname*". Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856).  
  
 Für MFC\-Dispatchschnittstellen nicht verfügbar.  
  
 **Zusätzliche Attribute**  
 Für MFC\-Dispatchschnittstellen nicht verfügbar.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|**hidden**|Zeigt an, dass die Methode existiert, in einem benutzerorientierten Browser jedoch nicht angezeigt werden sollte.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861).|  
|**source**|Zeigt an, dass ein Member der Methode eine Ereignisquelle ist.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [source](http://msdn.microsoft.com/library/windows/desktop/aa367166).|  
|`local`|Signalisiert dem MIDL\-Compiler, dass es sich nicht um eine Remotemethode handelt.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [local](http://msdn.microsoft.com/library/windows/desktop/aa367071).|  
|**restricted**|Zeigt an, dass die Methode nicht frei aufgerufen werden kann.  Weitere Informationen finden Sie in der *MIDL\- Referenz* unter [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157).|  
|**vararg**|Gibt an, dass die Methode eine variable Anzahl von Argumenten aufnimmt.  Dazu muss das letzte Argument ein sicheres Array vom Typ **VARIANT** sein, das alle übrigen Argumente enthält.  Weitere Informationen finden Sie in der *MIDL\-Referenz* unter [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304).|  
  
## Siehe auch  
 [Hinzufügen einer Methode](../ide/adding-a-method-visual-cpp.md)   
 [Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md)