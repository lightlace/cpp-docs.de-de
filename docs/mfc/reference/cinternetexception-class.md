---
title: "CInternetException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetException class"
  - "Ausnahmebehandlung, Internet operations"
  - "Ausnahmen, Internet"
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CInternetException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahmebedingung dar, die einem Internet\-Vorgang verknüpft ist.  
  
## Syntax  
  
```  
class CInternetException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetException::CInternetException](../Topic/CInternetException::CInternetException.md)|Erstellt ein `CInternetException`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CInternetException::m\_dwContext](../Topic/CInternetException::m_dwContext.md)|Der Kontextwert zugeordnet mit dem Vorgang, der die Ausnahme verursacht hat.|  
|[CInternetException::m\_dwError](../Topic/CInternetException::m_dwError.md)|Der Fehler, der die Ausnahme verursacht hat.|  
  
## Hinweise  
 Die `CInternetException`\-Klasse enthält zwei öffentliche Datenmember: ein enthält den Fehlercode Ausnahme zugeordnete an, und das andere enthält den Kontextbezeichner der Internetanwendung an, die mit dem Fehler verknüpft ist.  
  
 Weitere Informationen zu Kontextbezeichner für Internetanwendungen, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)