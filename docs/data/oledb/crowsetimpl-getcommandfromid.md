---
title: "CRowsetImpl::GetCommandFromID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl::GetCommandFromID"
  - "GetCommandFromID"
  - "CRowsetImpl.GetCommandFromID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandFromID-Methode"
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::GetCommandFromID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, um, wenn einer oder beide Parameter Zeichenfolgenwerte enthalten, und wenn ja Kopien, die Zeichenfolgenwerte in den Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
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
 Diese Methode wird durch eine statische Aufwärtsumwandlung vom `CRowsetImpl` aufgerufen, um die Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  Standardmäßig überprüft diese Methode, um zu sehen, wenn jeder oder beide Parameter Zeichenfolgenwerte enthalten.  Wenn sie enthalten, Zeichenfolgenwerte Kopien dieser Methode die Zeichenfolgenwerte in den Datenmembern.  Durch das Platzieren einer Methode mit dieser Signatur in der von `CRowsetImpl` abgeleiteten Klasse, die Methode wird anstelle der Basisimplementierung aufgerufen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CRowsetImpl\-Klasse](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)