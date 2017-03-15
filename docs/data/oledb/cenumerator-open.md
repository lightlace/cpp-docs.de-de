---
title: "CEnumerator::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CEnumerator.Open"
  - "CEnumerator::Open"
  - "ATL::CEnumerator::Open"
  - "CEnumerator.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: b22821a0-257a-4543-ad0c-2649d4ac092e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CEnumerator::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Umschließt den Moniker für den Enumerator, sofern festgelegt wird, ruft das Rowset für den Enumerator durch Aufrufen von [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx) ab.  
  
## Syntax  
  
```  
  
      HRESULT Open(   
   LPMONIKER pMoniker    
) throw( );  
HRESULT Open(   
   const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR    
) throw( );  
HRESULT Open(   
   const CEnumerator& enumerator    
) throw( );  
```  
  
#### Parameter  
 `pMoniker`  
 \[in\] Ein Zeiger auf einen Moniker für einen Enumerator.  
  
 *pClsid*  
 \[in\] Ein Zeiger auf **CLSID** eines Enumerators.  
  
 `enumerator`  
 \[in\] Einen Verweis auf einen Enumerator.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CEnumerator\-Klasse](../../data/oledb/cenumerator-class.md)