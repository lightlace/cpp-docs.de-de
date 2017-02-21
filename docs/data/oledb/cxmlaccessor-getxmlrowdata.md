---
title: "CXMLAccessor::GetXMLRowData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor::GetXMLRowData"
  - "ATL.CXMLAccessor.GetXMLRowData"
  - "CXMLAccessor::GetXMLRowData"
  - "CXMLAccessor.GetXMLRowData"
  - "GetXMLRowData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLRowData-Methode"
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CXMLAccessor::GetXMLRowData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den gesamten Inhalt einer Tabelle als Zeichenfolgendaten im XML\-Format, nach Zeile ab.  
  
## Syntax  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### Parameter  
 `strOutput`  
 \[out\] Einen Verweis auf einen Puffer, der die Tabellendaten enthält abgerufen werden.  Die Daten werden als Zeichenfolgendaten mit XML\-Tagnamen formatiert, die die Spaltennamen des Datenspeichers übereinstimmen.  
  
 *bAppend*  
 \[in\] Ein boolescher Wert, ob eine Zeichenfolge zum Ende der Ausgabedaten angefügt werden.  
  
## Rückgabewert  
 Einer der Standard\- `HRESULT`\-Werte.  
  
## Hinweise  
 Im Folgenden wird gezeigt, wie der Zeilendaten in XML formatiert werden.  Nächstes `DATA` stellt die Zeilendaten dar.  Verwendungs\-Verschiebungsmethoden, der an die gewünschte Zeile zu wechseln.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CXMLAccessor\-Klasse](../../data/oledb/cxmlaccessor-class.md)