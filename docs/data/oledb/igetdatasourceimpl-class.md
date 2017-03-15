---
title: "IGetDataSourceImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IGetDataSourceImpl"
  - "ATL.IGetDataSourceImpl<T>"
  - "ATL.IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IGetDataSourceImpl-Klasse"
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IGetDataSourceImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung des [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx)\-Objekts bereit.  
  
## Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IGetDataSourceImpl` abgeleitet.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetDataSource](../../data/oledb/igetdatasourceimpl-getdatasource.md)|Gibt einen Schnittstellenzeiger auf dem Datenquellenobjekt zurück, das die Sitzung erstellt hat.|  
  
## Hinweise  
 Dies ist eine erforderliche Schnittstelle auf der Sitzungs\- zum Abrufen eines Schnittstellenzeigers dem Datenquellenobjekt.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)