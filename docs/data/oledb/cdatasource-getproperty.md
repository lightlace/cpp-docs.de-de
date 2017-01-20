---
title: "CDataSource::GetProperty"
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
  - "ATL::CDataSource::GetProperty"
  - "ATL.CDataSource.GetProperty"
  - "CDataSource.GetProperty"
  - "CDataSource::GetProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperty-Methode"
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Wert einer angegebenen Eigenschaft für das verbundene Datenquellenobjekt zurück.  
  
## Syntax  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### Parameter  
 `guid`  
 \[in\] Eine GUID, die dem Eigenschaftensatz angegeben, dass der Eigenschaft zurückgibt.  
  
 `propid`  
 \[in\] Eigenschafts\-ID, damit die Eigenschaft zurückgegeben wird.  
  
 *pVariant*  
 \[out\] Ein Zeiger an eine Variante, in der **GetProperty** der Wert der Eigenschaft zurückgibt.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Um mehrere Eigenschaften abzurufen, verwenden Sie [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)