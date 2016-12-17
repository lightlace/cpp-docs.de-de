---
title: "IRowsetImpl::CreateRow"
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
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
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