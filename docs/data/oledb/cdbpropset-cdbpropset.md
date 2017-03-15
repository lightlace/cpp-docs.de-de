---
title: "CDBPropSet::CDBPropSet | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropSet.CDBPropSet"
  - "CDBPropSet::CDBPropSet"
  - "ATL::CDBPropSet::CDBPropSet"
  - "ATL.CDBPropSet.CDBPropSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropSet-Klasse, Konstruktor"
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDBPropSet::CDBPropSet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der \-Konstruktor.  Initialisiert **rgProperties**, **cProperties** und **guidPropertySet** Felder der Struktur unter [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx).  
  
## Syntax  
  
```  
  
      CDBPropSet(  
   const GUID& guid   
);  
CDBPropSet(   
   const CDBPropSet& propset    
);  
CDBPropSet( );  
```  
  
#### Parameter  
 `guid`  
 \[in\] Eine GUID verwendet, um das **guidPropertySet** Feld zu initialisieren.  
  
 *propset*  
 \[in\] ein anderes `CDBPropSet`\-Objekt für Kopienkonstruktion.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDBPropSet\-Klasse](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)