---
title: "CNotSupportedException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CNotSupportedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNotSupportedException class"
  - "Ausnahmen, not supported"
  - "unsupported features"
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CNotSupportedException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahme dar, die das Ergebnis eines Anforderung für eine nicht unterstützte Funktion ist.  
  
## Syntax  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](../Topic/CNotSupportedException::CNotSupportedException.md)|Erstellt ein `CNotSupportedException`\-Objekt.|  
  
## Hinweise  
 Keine weitere Qualifizierung ist erforderlich oder möglich.  
  
 Weitere Informationen zur Verwendung von `CNotSupportedException`, finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)