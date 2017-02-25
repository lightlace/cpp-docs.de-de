---
title: "CInvalidArgException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInvalidArgException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInvalidArgException class"
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CInvalidArgException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine ungültige ArgumentAusnahmebedingung dar.  
  
## Syntax  
  
```  
  
class CInvalidArgException : public CSimpleException  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](../Topic/CInvalidArgException::CInvalidArgException.md)|Der \-Konstruktor.|  
  
## Hinweise  
 Ein Objekt `CInvalidArgException` stellt eine ungültige ArgumentAusnahmebedingung dar.  
  
 Weitere Informationen zur Ausnahmebehandlung, finden Sie im Thema [CExceptions\-Klasse](../../mfc/reference/cexception-class.md) und [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## Anforderungen  
 **Header:** afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSimpleException Class](../../mfc/reference/csimpleexception-class.md)