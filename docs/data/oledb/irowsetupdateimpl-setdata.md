---
title: "IRowsetUpdateImpl::SetData"
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
  - "SetData"
  - "IRowsetUpdateImpl::SetData"
  - "IRowsetUpdateImpl.SetData"
  - "ATL::IRowsetUpdateImpl::SetData"
  - "ATL.IRowsetUpdateImpl.SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData-Methode"
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt Datenwerte in einer oder mehreren Spalten fest.  
  
## Syntax  
  
```  
  
      STDMETHOD ( SetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData   
);  
```  
  
#### Parameter  
 Siehe [IRowsetChange::SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Diese Methode überschreibt die [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md)\-Methode aber das Einschließungszwischenspeichern von ursprünglichen Daten, um entweder das direkte oder träge Verarbeitung des Vorgangs zu ermöglichen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetUpdateImpl\-Klasse](../../data/oledb/irowsetupdateimpl-class.md)