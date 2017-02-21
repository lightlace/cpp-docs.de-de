---
title: "CAccessorBase::IsAutoAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsAutoAccessor"
  - "CAccessorBase.IsAutoAccessor"
  - "CAccessorBase::IsAutoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsAutoAccessor-Methode"
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::IsAutoAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt true zurück, wenn Daten automatisch den Accessor während eines Verschiebungsvorgangs abgerufen werden.  
  
## Syntax  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### Parameter  
 `nAccessor`  
 \[in\] Die NullOffsetzahl für den Accessor.  
  
## Rückgabewert  
 Gibt **true** zurück, wenn der Accessor ein ob ist.  Andernfalls wird **false** zurückgegeben.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CAccessorBase\-Klasse](../../data/oledb/caccessorbase-class.md)