---
title: "IRowsetLocateImpl::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetLocateImpl.Compare"
  - "IRowsetLocateImpl::Compare"
  - "IRowsetLocateImpl.Compare"
  - "ATL::IRowsetLocateImpl::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare-Methode"
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Lesezeichen.  
  
## Syntax  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### Parameter  
 Siehe [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Alle der Lesezeichen kann ein standardmäßiges OLE DB\-definiertes [Standardlesezeichen](https://msdn.microsoft.com/en-us/library/ms712954.aspx) \(**DBBMK\_FIRST**, **DBBMK\_LAST** oder **DBBMK\_INVALID**\).  Der Wert, der von `pComparison` zurückgegeben wird, gibt der Beziehung zwischen den beiden Lesezeichen an:  
  
-   **DBCOMPARE\_LT** \(`cbBookmark1` ist vor `cbBookmark2`.\)  
  
-   **DBCOMPARE\_EQ** \(`cbBookmark1` entspricht `cbBookmark2`.\)  
  
-   **DBCOMPARE\_GT** \(`cbBookmark1` wird nach `cbBookmark2`.\)  
  
-   **DBCOMPARE\_NE** \(der Lesezeichen sind gleich und. nicht geordnet\)  
  
-   **DBCOMPARE\_NOTCOMPARABLE** \(der Lesezeichen können nicht verglichen werden.\)  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetLocateImpl\-Klasse](../../data/oledb/irowsetlocateimpl-class.md)