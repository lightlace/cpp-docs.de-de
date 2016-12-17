---
title: "CRowsetImpl::ValidateCommandID"
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
  - "CRowsetImpl.ValidateCommandID"
  - "CRowsetImpl::ValidateCommandID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ValidateCommandID-Methode"
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::ValidateCommandID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, überprüft, ob jedes oder sowohl **DBID**s Zeichenfolgenwerte und wenn ja enthalten, kopiert sie den Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
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
 Diese Methode wird durch eine statische Aufwärtsumwandlung vom `CRowsetImpl` aufgerufen, um die Datenmember [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  Standardmäßig überprüft diese Methode, um zu sehen, wenn jedes oder sowohl **DBID**s Zeichenfolgenwerte und wenn ja enthalten, kopiert sie den Datenmember.  Durch das Platzieren einer Methode mit dieser Signatur in der von `CRowsetImpl` abgeleiteten Klasse, die Methode wird anstelle der Basisimplementierung aufgerufen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [CRowsetImpl\-Klasse](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)