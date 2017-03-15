---
title: "IDBPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl.SetProperties"
  - "SetProperties"
  - "IDBPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties-Methode"
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt Eigenschaften in die Datenquellen\- und Initialisierungseigenschaftengruppen, für Datenquellenobjekte oder die Initialisierungseigenschaftengruppe, für Enumeratoren fest.  
  
## Syntax  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### Parameter  
 Siehe [IDBProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Wenn der Anbieter initialisiert wird, gibt diese Methode die Werte von Eigenschaften in **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT**\-Eigenschaftengruppen für das Datenquellenobjekt.  Wenn der Anbieter nicht initialisiert wird, wird er nur **DBPROPSET\_DBINIT** Gruppeneigenschaften fest.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBPropertiesImpl\-Klasse](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)