---
title: "CRowset::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>.Compare"
  - "CRowset<TAccessor>::Compare"
  - "ATL.CRowset<TAccessor>.Compare"
  - "ATL::CRowset<TAccessor>::Compare"
  - "CRowset.Compare"
  - "ATL::CRowset::Compare"
  - "ATL.CRowset.Compare"
  - "CRowset::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare-Methode"
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Lesezeichen mit [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).  
  
## Syntax  
  
```  
  
      HRESULT Compare(   
   const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison    
) const throw( );  
```  
  
#### Parameter  
 *Lesezeichen1*  
 \[in\] das erste Lesezeichen zu vergleichen.  
  
 *Lesezeichen2*  
 \[in\] Das zweite Lesezeichen zu vergleichen.  
  
 `pComparison`  
 \[out\] Ein Zeiger auf das Ergebnis des Vergleichs.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale `IRowsetLocate`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetLocate** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 Informationen zur Verwendung kennzeichnet in Consumern, finden Sie unter [Verwenden von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)