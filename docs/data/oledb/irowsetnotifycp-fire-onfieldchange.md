---
title: "IRowsetNotifyCP::Fire_OnFieldChange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Fire_OnFieldChange"
  - "ATL::IRowsetNotifyCP::Fire_OnFieldChange"
  - "ATL.IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP::Fire_OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fire_OnFieldChange-Methode"
ms.assetid: 03dad058-8d4f-4113-aea4-ef7764eab9ec
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetNotifyCP::Fire_OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überträgt [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) ein Ereignis, um Consumern zu einer Änderung am Wert einer Spalte zu benachrichtigen.  
  
## Syntax  
  
```  
  
      HRESULT Fire_OnFieldChange(  
   IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### Parameter  
 Siehe [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetNotifyCP\-Klasse](../../data/oledb/irowsetnotifycp-class.md)