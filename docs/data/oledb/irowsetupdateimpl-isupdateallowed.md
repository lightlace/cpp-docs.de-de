---
title: "IRowsetUpdateImpl::IsUpdateAllowed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetUpdateImpl::IsUpdateAllowed"
  - "IRowsetUpdateImpl.IsUpdateAllowed"
  - "IsUpdateAllowed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsUpdateAllowed-Methode"
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::IsUpdateAllowed
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überschreiben Sie diese Methode, um für Sicherheit, Integrität, z. B vor Updates.  
  
## Syntax  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### Parameter  
 *status*  
 \[in\] der Status der ausstehenden Operationen für Zeilen.  
  
 *hRowUpdate*  
 \[in\] behandeln Sie für die Zeilen, die der Benutzer aktualisieren möchte.  
  
 *pRowStatus*  
 \[out\] der Status zurückgegeben dem Benutzer.  
  
## Hinweise  
 Wenn Sie feststellen, dass ein Update ermöglicht werden soll, gibt `S_OK` zurück; gibt andernfalls **E\_FAIL** zurück.  Wenn Sie ein Update kann, müssen Sie auch **DBROWSTATUS** in [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) auf entsprechende [Zeilenstatus](https://msdn.microsoft.com/en-us/library/ms722752.aspx) festlegen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)