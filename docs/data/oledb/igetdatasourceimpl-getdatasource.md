---
title: "IGetDataSourceImpl::GetDataSource"
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
  - "GetDataSource"
  - "IGetDataSourceImpl.GetDataSource"
  - "IGetDataSourceImpl::GetDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataSource-Methode"
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IGetDataSourceImpl::GetDataSource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Schnittstellenzeiger auf dem Datenquellenobjekt zurück, das die Sitzung erstellt hat.  
  
## Syntax  
  
```  
  
      STDMETHOD(GetDataSource)(   
   REFIID riid,   
   IUnknown ** ppDataSource    
);  
```  
  
#### Parameter  
 Siehe [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Wird, wenn Sie Eigenschaften im Datenquellenobjekt zugreifen müssen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IGetDataSourceImpl\-Klasse](../../data/oledb/igetdatasourceimpl-class.md)