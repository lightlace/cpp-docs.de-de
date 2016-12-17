---
title: "CBulkRowset::MoveToBookmark"
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
  - "CBulkRowset<TAccessor>::MoveToBookmark"
  - "CBulkRowset.MoveToBookmark"
  - "MoveToBookmark"
  - "ATL.CBulkRowset.MoveToBookmark"
  - "CBulkRowset::MoveToBookmark"
  - "ATL::CBulkRowset<TAccessor>::MoveToBookmark"
  - "ATL::CBulkRowset::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark-Methode"
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Zeile ab, die von ein Lesezeichen gekennzeichnet oder die Zeile an einem angegebenen Offset \(`lSkip`\) von diesem Lesezeichen.  
  
## Syntax  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### Parameter  
 `bookmark`  
 \[in\] a\-Lesezeichen, das die Position markiert, von dem Sie Daten abrufen möchten.  
  
 `lSkip`  
 \[in\] Die Zahlenanzahl von Zeilen im Lesezeichen die Zielzeile.  Wenn `lSkip` null ist, ist die erste Zeile abgerufene die mit Lesezeichen versehene Zeile.  Wenn `lSkip` 1 ist, ist die erste Zeile abgerufene die Zeile nach der mit Lesezeichen versehene Zeile.  Wenn `lSkip` \- 1, während die erste Zeile ist die Zeile vor der mit Lesezeichen versehene Zeile.  
  
## Rückgabewert  
 Siehe [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBulkRowset\-Klasse](../../data/oledb/cbulkrowset-class.md)