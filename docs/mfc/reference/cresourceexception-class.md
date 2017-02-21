---
title: "CResourceException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CResourceException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CResourceException class"
  - "Ausnahmen, Ressource"
  - "resource allocation exception"
  - "resource exceptions"
  - "Ressourcen [C++], Reservieren"
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CResourceException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird generiert, wenn Windows eine angeforderte Ressource nicht finden oder zuordnen kann.  
  
## Syntax  
  
```  
class CResourceException : public CSimpleException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CResourceException::CResourceException](../Topic/CResourceException::CResourceException.md)|Erstellt ein `CResourceException`\-Objekt.|  
  
## Hinweise  
 Keine weitere Qualifizierung ist erforderlich oder möglich.  
  
 Weitere Informationen zur Verwendung von `CResourceException`, finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)