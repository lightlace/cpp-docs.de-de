---
title: "CAccessorBase::GetHAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetHAccessor"
  - "CAccessorBase::GetHAccessor"
  - "CAccessorBase.GetHAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetHAccessor-Methode"
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::GetHAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft das Accessorhandle eines angegebenen Accessor ab.  
  
## Syntax  
  
```  
  
      HACCESSOR GetHAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### Parameter  
 `nAccessor`  
 \[in\] Die NullOffsetzahl für den Accessor.  
  
## Rückgabewert  
 Das Accessorhandle.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CAccessorBase\-Klasse](../../data/oledb/caccessorbase-class.md)