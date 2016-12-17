---
title: "ICommandPropertiesImpl::GetProperties"
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
  - "ICommandPropertiesImpl::GetProperties"
  - "ICommandPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties-Methode"
ms.assetid: 1bee5f1b-bd08-435a-956a-e4cebcdf5d5e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt alle angeforderten Eigenschaftensätzen mithilfe der Eigenschaftenzuordnung des Befehls zurück.  
  
## Syntax  
  
```  
  
      STDMETHOD(GetProperties)(   
   const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets    
);  
```  
  
#### Parameter  
 Siehe [ICommandProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms723119.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Siehe [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [ICommandPropertiesImpl\-Klasse](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)