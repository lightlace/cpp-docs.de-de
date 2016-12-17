---
title: "CDataSource::GetProperties"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDataSource::GetProperties"
  - "ATL.CDataSource.GetProperties"
  - "CDataSource.GetProperties"
  - "ATL::CDataSource::GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties-Methode"
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Eigenschafteninformationen zurück, die für das verbundene Datenquellenobjekt angefordert werden.  
  
## Syntax  
  
```  
  
      HRESULT GetProperties(   
   ULONG ulPropIDSets,   
   const DBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets    
) const throw( );  
```  
  
#### Parameter  
 Siehe [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in *der OLE DB\-Programmierreferenz* in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Um eine einzelne Eigenschaft abzurufen, verwenden Sie [GetProperty](../../data/oledb/cdatasource-getproperty.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)