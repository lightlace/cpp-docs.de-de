---
title: "CBookmark::SetBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>::SetBookmark"
  - "ATL.CBookmark<0>.SetBookmark"
  - "CBookmark<0>.SetBookmark"
  - "SetBookmark"
  - "ATL::CBookmark::SetBookmark"
  - "ATL::CBookmark<0>::SetBookmark"
  - "CBookmark.SetBookmark"
  - "ATL.CBookmark.SetBookmark"
  - "CBookmark::SetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBookmark-Methode"
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::SetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopiert den Lesezeichenwert, der von `pBuffer` in den Puffer `CBookmark` verwiesen wird und die Puffergröße auf `nSize` fest.  
  
## Syntax  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### Parameter  
 *nSize*  
 \[in\] Die Größe des Lesezeichenpuffers.  
  
 `pBuffer`  
 \[in\] Ein Zeiger auf das Bytearray, das den Lesezeichenwert enthält.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Funktion ist nur verfügbar in **CBookmark \<0\>**.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBookmark\-Klasse](../../data/oledb/cbookmark-class.md)