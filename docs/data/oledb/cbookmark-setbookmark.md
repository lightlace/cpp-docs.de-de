---
title: "CBookmark::SetBookmark"
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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