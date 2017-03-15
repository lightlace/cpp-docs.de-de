---
title: "IRowsetImpl::RestartPosition | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.RestartPosition"
  - "IRowsetImpl::RestartPosition"
  - "RestartPosition"
  - "ATL::IRowsetImpl::RestartPosition"
  - "IRowsetImpl.RestartPosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RestartPosition-Methode"
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::RestartPosition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet die folgenden Abrufposition an seine Ausgangsposition neu an; das heißt, die Position, als das Rowset zuerst erstellt wurde.  
  
## Syntax  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### Parameter  
 Siehe [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Die Rowsetposition undefiniert, bis **GetNextRow** aufgerufen wird.  Sie können in ein rowet rückwärts wechseln, indem Sie [RestartPosition](#vcrefirowsetimplrestartposition) aufrufen und abrufen oder rückwärts wechseln.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)