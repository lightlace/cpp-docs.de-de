---
title: "_AtlCreateWndData Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_AtlCreateWndData"
  - "ATL._AtlCreateWndData"
  - "_AtlCreateWndData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AtlCreateWndData structure"
  - "AtlCreateWndData structure"
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _AtlCreateWndData Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Struktur enthält Klasseninstanzdaten im Fenstercode in ATL.  
  
## Syntax  
  
```  
  
      struct _AtlCreateWndData{  
   void* m_pThis;  
   DWORD m_dwThreadID;  
   _AtlCreateWndData* m_pNext;  
};  
```  
  
## Mitglieder  
 **m\_pThis**  
 Der **this** Zeiger verwendet, um Zugriff auf die Klasseninstanz in den Fensterprozeduren abzurufen.  
  
 `m_dwThreadID`  
 Die Thread\-IDs der aktuellen Klasseninstanz.  
  
 **m\_pNext**  
 Zeiger auf den folgenden `_AtlCreateWndData`\-Objekt.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)