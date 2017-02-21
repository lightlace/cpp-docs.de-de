---
title: "COleException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleException class"
  - "Ausnahmen, OLE"
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahmebedingung dar, die einem OLE\-Vorgang verknüpft ist.  
  
## Syntax  
  
```  
class COleException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleException::Process](../Topic/COleException::Process.md)|Übersetzt eine abgefangene Ausnahme in einen OLE\-Rückgabecode.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleException::m\_sc](../Topic/COleException::m_sc.md)|Enthält den Statuscode, der den Grund für die Ausnahme angibt.|  
  
## Hinweise  
 Die `COleException`\-Klasse enthält einen öffentlichen Datenmember, der den Statuscode enthält, der den Grund für die Ausnahme angibt.  
  
 Im Allgemeinen sollten Sie ein `COleException`\-Objekt nicht direkt erstellen; stattdessen sollten Sie [AfxThrowOleException](../Topic/AfxThrowOleException.md) aufrufen.  
  
 Weitere Informationen zu Ausnahmen, finden Sie in Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE\-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [MFC\-Beispiel CALCDRIV](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)