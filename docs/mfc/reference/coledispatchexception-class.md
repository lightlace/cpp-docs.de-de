---
title: "COleDispatchException Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automatisierung, Ausnahmen"
  - "COleDispatchException class"
  - "Ausnahmen, OLE"
  - "OLE exceptions, to IDispatch interface"
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleDispatchException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Behandeln bestimmt zur Schnittstelle OLE `IDispatch`, die eine Schlüsselkomponente OLE\-Automatisierung ist.  
  
## Syntax  
  
```  
class COleDispatchException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleDispatchException::m\_dwHelpContext](../Topic/COleDispatchException::m_dwHelpContext.md)|Hilfekontext für Fehler.|  
|[COleDispatchException::m\_strDescription](../Topic/COleDispatchException::m_strDescription.md)|Mündliche Fehlerbeschreibung.|  
|[COleDispatchException::m\_strHelpFile](../Topic/COleDispatchException::m_strHelpFile.md)|Mit `m_dwHelpContext` zu verwenden, Hilfedatei.|  
|[COleDispatchException::m\_strSource](../Topic/COleDispatchException::m_strSource.md)|Anwendung, die die Ausnahme generiert.|  
|[COleDispatchException::m\_wCode](../Topic/COleDispatchException::m_wCode.md)|`IDispatch` bestimmter \- Fehlercode.|  
  
## Hinweise  
 Wie die anderen Ausnahmeklassen, die von der `CException` Basisklasse abgeleitet werden, kann `COleDispatchException` mit **THROW**, `THROW_LAST`, **TRY**, **CATCH**, `AND_CATCH` und `END_CATCH`\-Makros verwendet werden.  
  
 Im Allgemeinen sollten Sie [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md) aufrufen, um ein Objekt `COleDispatchException` zu erstellen und auszulösen.  
  
 Weitere Informationen zu Ausnahmen, finden Sie in Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: OLE\-Ausnahmen](../../mfc/exceptions-ole-exceptions.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [MFC Sampling CALCDRIV](../../top/visual-cpp-samples.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException Class](../../mfc/reference/coleexception-class.md)