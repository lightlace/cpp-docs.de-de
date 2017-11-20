---
title: "CDBPropIDSet::SetGUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropIDSet.SetGUID"
  - "ATL::CDBPropIDSet::SetGUID"
  - "SetGUID"
  - "ATL.CDBPropIDSet.SetGUID"
  - "CDBPropIDSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetGUID-Methode"
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBPropIDSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt das GUID\-Feld in der **DBPROPIDSET**\-Struktur fest.  
  
## Syntax  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### Parameter  
 `guid`  
 \[in\] Eine GUID verwendet, um das **guidPropertySet** \- Feld der Struktur [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) festzulegen.  
  
## Hinweise  
 Dieses Feld kann von [Konstruktor](../../data/oledb/cdbpropidset-cdbpropidset.md) auch festgelegt werden.  Rufen Sie diese Funktion auf, wenn der Standardkonstruktor für diese Klasse verwenden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBPropIDSet\-Klasse](../../data/oledb/cdbpropidset-class.md)