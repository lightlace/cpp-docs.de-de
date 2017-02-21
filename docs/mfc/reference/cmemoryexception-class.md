---
title: "CMemoryException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Speicher"
  - "CMemoryException class"
  - "Ausnahmen, memory type"
  - "memory exceptions"
  - "Speicher, Ausnahmebehandlung"
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMemoryException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahmebedingung mit ungenügenden Arbeitsspeicher dar.  
  
## Syntax  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](../Topic/CMemoryException::CMemoryException.md)|Erstellt ein `CMemoryException`\-Objekt.|  
  
## Hinweise  
 Keine weitere Qualifizierung ist erforderlich oder möglich.  Arbeitsspeicherausnahmen werden automatisch von **new** ausgelöst.  Wenn Sie eigene Speicherfunktionen, mit `malloc` beispielsweise schreiben anschließend sind Sie für das Auslösen von Arbeitsspeicherausnahmen zuständig.  
  
 Weitere Informationen zu `CMemoryException`, finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)