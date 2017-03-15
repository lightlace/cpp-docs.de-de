---
title: "CRowset::GetDataHere | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::GetDataHere"
  - "CRowset<TAccessor>.GetDataHere"
  - "CRowset.GetDataHere"
  - "GetDataHere"
  - "CRowset::GetDataHere"
  - "ATL::CRowset::GetDataHere"
  - "ATL::CRowset<TAccessor>::GetDataHere"
  - "ATL.CRowset<TAccessor>.GetDataHere"
  - "ATL.CRowset.GetDataHere"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataHere-Methode"
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::GetDataHere
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Daten aus der aktuellen Zeile ab und platziert ihn in den angegebenen Puffer.  
  
## Syntax  
  
```  
  
      HRESULT GetDataHere(   
   int nAccessor,   
   void* pBuffer    
) throw( );  
```  
  
#### Parameter  
 `nAccessor`  
 \[in\] Die Indexnummer des für das Zugreifen Accessor zu verwenden, auf die Daten.  
  
 `pBuffer`  
 \[out\] in den a\-Puffer, um die Daten für den aktuellen Datensatz zu platzieren.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Ein Beispiel, wie diese Funktion verwendet werden, finden Sie unter [MultiRead\-Beispiel](../../top/visual-cpp-samples.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)