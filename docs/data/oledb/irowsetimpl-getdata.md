---
title: "IRowsetImpl::GetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.GetData"
  - "ATL::IRowsetImpl::GetData"
  - "IRowsetImpl::GetData"
  - "IRowsetImpl.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData-Methode [OLE DB]"
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Daten von der Zeilenkopie des Rowsets ab.  
  
## Syntax  
  
```  
  
      STDMETHOD( GetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData   
);  
```  
  
#### Parameter  
 Siehe [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 Einige Parameter entsprechen *den OLE DB Programmer's Reference\-Parametern* von verschiedenen Namen, die in **IRowset::GetData** beschrieben werden:  
  
|OLE DB\-Vorlagen\-Parameter|*OLE DB Programmer's Reference\-*\-Parameter|  
|---------------------------------|--------------------------------------------------|  
|*pDstData*|`pData`|  
  
## Hinweise  
 Behandelt auch Datenkonvertierung unter Verwendung der OLE DB\-Datenkonvertierung DLL.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)