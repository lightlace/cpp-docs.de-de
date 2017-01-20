---
title: "CXMLAccessor::GetXMLColumnData"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
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