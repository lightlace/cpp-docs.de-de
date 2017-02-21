---
title: "IRowsetChangeImpl::FlushData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetChangeImpl::FlushData"
  - "IRowsetChangeImpl.FlushData"
  - "FlushData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FlushData-Methode"
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetChangeImpl::FlushData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Overidden durch den Anbieter auf, um Daten in den Speicher zu übernehmen.  
  
## Syntax  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### Parameter  
 *hRowToFlush*  
 \[in\] Handle auf Linien für die Daten.  Der Typ dieser Linie wird von der *RowClass\-Vorlagenargument* der `IRowsetImpl`\-Klasse \(standardmäßig `CSimpleRow` \) bestimmt.  
  
 *hAccessorToFlush*  
 \[in\] Handle dem Accessor, der enthalten, das Binden Informationen und Typinformationen in den **PROVIDER\_MAP** \(siehe [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)\).  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetChangeImpl\-Klasse](../../data/oledb/irowsetchangeimpl-class.md)