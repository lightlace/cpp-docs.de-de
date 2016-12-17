---
title: "IOpenRowsetImpl::OpenRowset"
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
  - "OpenRowset"
  - "IOpenRowsetImpl::OpenRowset"
  - "IOpenRowsetImpl.OpenRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenRowset-Methode"
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IOpenRowsetImpl::OpenRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet und gibt ein Rowset zurückgegeben, das sämtliche Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.  
  
## Syntax  
  
```  
  
      HRESULT OpenRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset   
);  
```  
  
#### Parameter  
 Siehe [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Diese Methode wird nicht in ATLDB.H. gefunden.  Sie wird vom ATL\-Objekt\-Assistenten erstellt, wenn Sie einen Anbieter erstellen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IOpenRowsetImpl\-Klasse](../../data/oledb/iopenrowsetimpl-class.md)