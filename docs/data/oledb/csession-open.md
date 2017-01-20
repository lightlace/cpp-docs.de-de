---
title: "CSession::Open"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CSession::Open"
  - "CSession::Open"
  - "CSession.Open"
  - "ATL.CSession.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine neue Sitzung für das Datenquellenobjekt.  
  
## Syntax  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Parameter  
 `ds`  
 \[in\] die Datenquelle, die für die Sitzung geöffnet werden soll.  
  
 *pPropSet*  
 \[in\] strukturiert Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) das Einbinden von festgelegt werden Eigenschaften und Werte.  Siehe [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in *der OLE DB\-Programmierreferenz* in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ulPropSets`  
 \[in\] hat die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen in das *pPropSet*\-Argument.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Sie müssen das Datenquellenobjekt mit dem [CDataSource::Open](../../data/oledb/cdatasource-open.md) öffnen, bevor Sie es an `CSession::Open` übergeben.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CSession\-Klasse](../../data/oledb/csession-class.md)