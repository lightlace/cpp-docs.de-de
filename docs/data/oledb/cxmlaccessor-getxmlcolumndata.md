---
title: "CXMLAccessor::GetXMLColumnData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CXMLAccessor.GetXMLColumnData"
  - "CXMLAccessor::GetXMLColumnData"
  - "CXMLAccessor.GetXMLColumnData"
  - "ATL::CXMLAccessor::GetXMLColumnData"
  - "GetXMLColumnData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLColumnData-Methode"
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CXMLAccessor::GetXMLColumnData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Ständerinformationen einer Tabelle als Zeichenfolgendaten im XML\-Format, nach Spalten ab.  
  
## Syntax  
  
```  
  
      HRESULT GetXMLColumnData(   
   CSimpleStringW& strOutput    
) throw( );  
```  
  
#### Parameter  
 `strOutput`  
 \[out\] Einen Verweis auf einen Zeichenfolgenpuffer, der abgerufen werden Ständerinformationen enthält.  Die Zeichenfolge wird mit XML\-Tagnamen formatiert, die die Spaltennamen des Datenspeichers übereinstimmen.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Im Folgenden wird gezeigt, wie die Ständerinformationen in XML formatiert werden.  `type` gibt den Datentyp der Spalte an.  Beachten Sie dass die Datentypen basieren auf OLE DB\-Datentypen, nicht die der Datenbank, die zugegriffen wird.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CXMLAccessor\-Klasse](../../data/oledb/cxmlaccessor-class.md)