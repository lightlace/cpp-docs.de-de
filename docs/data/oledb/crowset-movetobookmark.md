---
title: "CRowset::MoveToBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset::MoveToBookmark"
  - "ATL::CRowset<TAccessor>::MoveToBookmark"
  - "ATL.CRowset.MoveToBookmark"
  - "ATL.CRowset<TAccessor>.MoveToBookmark"
  - "MoveToBookmark"
  - "CRowset::MoveToBookmark"
  - "CRowset.MoveToBookmark"
  - "CRowset<TAccessor>::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark-Methode"
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Zeile ab, die von ein Lesezeichen gekennzeichnet oder die Zeile an einem angegebenen Offset \(`lSkip`\) von diesem Lesezeichen.  
  
## Syntax  
  
```  
  
      HRESULT MoveToBookmark(   
   const CBookmarkBase& bookmark,   
   LONG lSkip = 0    
) throw( );  
```  
  
#### Parameter  
 `bookmark`  
 \[in\] a\-Lesezeichen, das die Position markiert, von dem Sie Daten abrufen möchten.  
  
 `lSkip`  
 \[in\] Die Zahlenanzahl von Zeilen im Lesezeichen die Zielzeile.  Wenn `lSkip` null ist, ist die erste Zeile abgerufene die mit Lesezeichen versehene Zeile.  Wenn `lSkip` 1 ist, ist die erste Zeile abgerufene die Zeile nach der mit Lesezeichen versehene Zeile.  Wenn `lSkip` \- 1, während die erste Zeile ist die Zeile vor der mit Lesezeichen versehene Zeile.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale `IRowsetLocate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetLocate** auf `VARIANT_TRUE` festlegen und **DBPROP\_CANFETCHBACKWARDS** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 Informationen zur Verwendung kennzeichnet in Consumern, finden Sie unter [Verwenden von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)