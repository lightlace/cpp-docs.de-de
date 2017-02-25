---
title: "CDBPropSet::SetGUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDBPropSet.SetGUID"
  - "CDBPropSet.SetGUID"
  - "ATL::CDBPropSet::SetGUID"
  - "SetGUID"
  - "CDBPropSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty-Methode"
  - "SetGUID-Methode"
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBPropSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt **guidPropertySet** das Feld in der **DBPROPSET**\-Struktur fest.  
  
## Syntax  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### Parameter  
 `guid`  
 \[in\] Eine GUID verwendet, um das **guidPropertySet** \- Feld der Struktur [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) festzulegen.  
  
## Hinweise  
 Dieses Feld kann von [Konstruktor](../../data/oledb/cdbpropset-cdbpropset.md) auch festgelegt werden.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBPropSet\-Klasse](../../data/oledb/cdbpropset-class.md)