---
title: "COleDispatchDriver Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchDriver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation clients, implementing Automation"
  - "COleDispatchDriver class"
  - "OLE dispatch interface"
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleDispatchDriver Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Clientseite der OLE\-Automatisierung.  
  
## Syntax  
  
```  
class COleDispatchDriver  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](../Topic/COleDispatchDriver::COleDispatchDriver.md)|Erstellt ein `COleDispatchDriver`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](../Topic/COleDispatchDriver::AttachDispatch.md)|Fügt eine `IDispatch` Verbindung zum `COleDispatchDriver`\-Objekt.|  
|[COleDispatchDriver::CreateDispatch](../Topic/COleDispatchDriver::CreateDispatch.md)|Erstellt eine `IDispatch` Verbindung und fügt sie dem `COleDispatchDriver`\-Objekt.|  
|[COleDispatchDriver::DetachDispatch](../Topic/COleDispatchDriver::DetachDispatch.md)|Trennt eine `IDispatch` Verbindung, ohne sie freizugeben.|  
|[COleDispatchDriver::GetProperty](../Topic/COleDispatchDriver::GetProperty.md)|Ruft eine Automatisierungseigenschaft ab.|  
|[COleDispatchDriver::InvokeHelper](../Topic/COleDispatchDriver::InvokeHelper.md)|Hilfe für aufrufende Automatisierungsmethoden.|  
|[COleDispatchDriver::ReleaseDispatch](../Topic/COleDispatchDriver::ReleaseDispatch.md)|Gibt eine `IDispatch` Verbindung frei.|  
|[COleDispatchDriver::SetProperty](../Topic/COleDispatchDriver::SetProperty.md)|Legt eine Automatisierungseigenschaft fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchDriver::operator \=](../Topic/COleDispatchDriver::operator%20=.md)|Kopiert den Quellwert in das `COleDispatchDriver`\-Objekt.|  
|[COleDispatchDriver::operator LPDISPATCH](../Topic/COleDispatchDriver::operator%20LPDISPATCH.md)|Greift auf den zugrunde liegenden `IDispatch` Zeiger auf.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchDriver::m\_bAutoRelease](../Topic/COleDispatchDriver::m_bAutoRelease.md)|Gibt an, ob `IDispatch` während `ReleaseDispatch` freigibt oder zerstört werden.|  
|[COleDispatchDriver::m\_lpDispatch](../Topic/COleDispatchDriver::m_lpDispatch.md)|Gibt den Zeiger auf die `IDispatch`\-Schnittstelle, die zu diesem `COleDispatchDriver` angefügt wird.|  
  
## Hinweise  
 `COleDispatchDriver` hat keine Basisklasse.  
  
 OLE\-Dispatchschnittstellen ermöglichen den Zugriff auf Methoden und Eigenschaften eines Objekts.  Memberfunktionen von `COleDispatchDriver` Anfügen, Trennen, erstellen und eine Dispatch\-Verbindung des Typs `IDispatch` frei.  Andere Memberfunktionen Variablenargumentlisten verwenden, um das Aufrufen von **IDispatch::Invoke** zu vereinfachen.  
  
 Diese Klasse kann direkt verwendet werden, sie ist im Allgemeinen nur durch die Klassen, die vom Hinzufügens\-Klassenassistenten erstellt werden.  Wenn Sie erstellen, werden neue C\+\+, indem eine Typbibliothek, neue Klassen importieren, werden von abgeleitet `COleDispatchDriver`.  
  
 Weitere Informationen zur Verwendung von `COleDispatchDriver`, finden Sie:  
  
-   [Automatisierungs\-Clienten](../../mfc/automation-clients.md)  
  
-   [Automatisierungsserver](../../mfc/automation-servers.md)  
  
## Vererbungshierarchie  
 `COleDispatchDriver`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [MFC\-Beispiel CALCDRIV](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel ACDual](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)