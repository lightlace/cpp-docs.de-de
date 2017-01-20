---
title: "CBookmark::CBookmark"
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
  - "CBookmark<0>.CBookmark<0>"
  - "CBookmark::CBookmark"
  - "ATL.CBookmark.CBookmark"
  - "CBookmark.CBookmark"
  - "CBookmark"
  - "ATL::CBookmark<0>::CBookmark<0>"
  - "ATL.CBookmark<0>.CBookmark<0>"
  - "CBookmark<0>::CBookmark<0>"
  - "ATL::CBookmark::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark-Klasse, Konstruktor"
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CBookmark::CBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der \-Konstruktor.  
  
## Syntax  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### Parameter  
 `nSize`  
 \[in\] Größe des Lesezeichenpuffers in Bytes.  
  
## Hinweise  
 Die erste Funktion legt den Puffer auf **NULL** und die Puffergröße auf 0 fest.  Die zweite Funktion legt die Puffergröße auf `nSize` und den Puffer auf Bytes ein Bytearray `nSize` fest.  
  
> [!NOTE]
>  Diese Funktion ist nur verfügbar in **CBookmark \<0\>**.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBookmark\-Klasse](../../data/oledb/cbookmark-class.md)