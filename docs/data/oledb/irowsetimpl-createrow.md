---
title: "IRowsetImpl::CreateRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl.CreateRow"
  - "ATL.IRowsetImpl.CreateRow"
  - "ATL::IRowsetImpl::CreateRow"
  - "CreateRow"
  - "IRowsetImpl::CreateRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRow-Methode"
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::CreateRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Hilfsmethode aufgerufen über [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md), um neuen **HROW** zuzuordnen.  
  
## Syntax  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
```  
  
#### Parameter  
 *lRowsOffset*  
 Cursorposition der Zeile, die erstellt wird.  
  
 *cRowsObtained*  
 Ein Verweis übergebene zurück an den Benutzer, der die Anzahl der den erstellten Zeilen angeben.  
  
 *rgRows*  
 Ein Array von **HROW**s zurückgegeben zum Aufrufer mit den neu erstellten Zeilenhandles.  
  
## Hinweise  
 Wenn die Zeile ist, dieses Methodenaufrufe [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und zurückgibt.  Andernfalls ordnet es einer neuen Instanz der RowClass\-Vorlagenvariable zu und fügt sie [m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md) hinzu.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)