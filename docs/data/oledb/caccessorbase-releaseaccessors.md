---
title: "CAccessorBase::ReleaseAccessors"
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
  - "CAccessorBase::ReleaseAccessors"
  - "CAccessorBase.ReleaseAccessors"
  - "ReleaseAccessors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessors-Methode"
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase::ReleaseAccessors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Befreit die Accessoren, die von der Klasse erstellt werden.  
  
## Syntax  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### Parameter  
 *pUnk*  
 \[in\] Ein Zeiger auf eine **IUnknown**\-Schnittstelle für das COM\-Objekt, für das die Accessoren erstellt wurden.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Wird von [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CAccessorBase\-Klasse](../../data/oledb/caccessorbase-class.md)