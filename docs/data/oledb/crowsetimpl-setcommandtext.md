---
title: "CRowsetImpl::SetCommandText | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.SetCommandText"
  - "CRowsetImpl::SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText-Methode"
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft Anschließend wird das **DBID**s in beiden Zeichenfolgen \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### Parameter  
 `pTableID`  
 \[in\] Ein Zeiger auf **DBID**, das die Tabelle ID darstellt  
  
 `pIndexID`  
 \[in\] Ein Zeiger auf **DBID**, das die ID darstellt Index  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Die **SetCommentText**\-Methode wird von `CreateRowset`, einer statischen vorlagenbasierter Methode von `IOpenRowsetImpl` aufgerufen.  
  
 Diese Methode delegiert die Arbeit, indem sie [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) durch einen Zeiger upcasted aufruft.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CRowsetImpl\-Klasse](../../data/oledb/crowsetimpl-class.md)