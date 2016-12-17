---
title: "CBulkRowset::MoveToRatio"
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
  - "CBulkRowset.MoveToRatio"
  - "ATL::CBulkRowset::MoveToRatio"
  - "MoveToRatio"
  - "CBulkRowset::MoveToRatio"
  - "ATL.CBulkRowset<TAccessor>.MoveToRatio"
  - "ATL::CBulkRowset<TAccessor>::MoveToRatio"
  - "ATL.CBulkRowset.MoveToRatio"
  - "CBulkRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio-Methode"
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Start\- Zeilen aus einer Bruchposition im Rowset.  
  
## Syntax  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### Parameter  
 `nNumerator`  
 \[in\] der Zähler verwendet, um festzustellen von der die Bruchposition, Daten abzurufen.  
  
 `nDenominator`  
 \[in\] der Nenner verwendet, um festzustellen von der die Bruchposition, Daten abzurufen.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 `MoveToRatio` ruft die ca. Zeilen entsprechend der folgenden Formel ab:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Dabei ist `RowsetSize` die Größe des Rowsets ist, gemessen in Zeilen.  Die Genauigkeit dieser Formel hängt vom bestimmten Anbieter ab.  Ausführliche Informationen finden Sie unter [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBulkRowset\-Klasse](../../data/oledb/cbulkrowset-class.md)