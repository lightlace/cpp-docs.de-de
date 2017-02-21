---
title: "CArchiveException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArchiveException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archive exceptions [C++]"
  - "CArchiveException class"
  - "exceptions [C++], archive"
  - "exceptions [C++], Serialisierung"
  - "Serialisierung [C++], Ausnahmen"
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CArchiveException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine SerialisierungsAusnahmebedingung dar  
  
## Syntax  
  
```  
class CArchiveException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](../Topic/CArchiveException::CArchiveException.md)|Erstellt ein `CArchiveException`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CArchiveException::m\_cause](../Topic/CArchiveException::m_cause.md)|Gibt die Ausnahmeursache an.|  
|[CArchiveException::m\_strFileName](../Topic/CArchiveException::m_strFileName.md)|Gibt den Namen der Datei für diese Ausnahmebedingung an.|  
  
## Hinweise  
 Die `CArchiveException`\-Klasse enthält einen öffentlichen Datenmember, der die Ursache der Ausnahme angibt.  
  
 `CArchiveException`\-Objekte werden und ausgelösten innere [CArchive](../../mfc/reference/carchive-class.md)\-Memberfunktionen erstellt.  Sie können auf diese Objekte im Rahmen eines Ausdrucks **CATCH** zugreifen.  Der Ursachencode ist unabhängig des Betriebssystems.  Weitere Informationen über die Ausnahmeverarbeitung, finden Sie unter [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CArchive Class](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)