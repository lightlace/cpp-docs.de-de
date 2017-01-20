---
title: "IDBPropertiesImpl::GetProperties"
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
  - "IDBPropertiesImpl::GetProperties"
  - "IDBPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties-Methode"
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Werten von Eigenschaften in die Datenquellen\-, Datenquellen\-Informationens\- und Initialisierungseigenschaftengruppen zurück, die gerade im Datenquellenobjekt oder die Werte von Eigenschaften in der Initialisierungseigenschaftengruppe festgelegt werden, die derzeit auf den Enumerator festgelegt werden.  
  
## Syntax  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### Parameter  
 Siehe [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in der *OLE* DB\-Programmierreferenz.  
  
 Einige Parameter entsprechen *den OLE DB Programmer's Reference\-Parametern* von verschiedenen Namen, die in **IDBProperties::GetProperties** beschrieben werden:  
  
|OLE DB\-Vorlagen\-Parameter|*OLE DB Programmer's Reference\-*\-Parameter|  
|---------------------------------|--------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## Hinweise  
 Wenn der Anbieter initialisiert wird, gibt diese Methode die Werte von Eigenschaften in **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT**\-Eigenschaftengruppen, die gerade im Datenquellenobjekt festgelegt werden.  Wenn der Anbieter nicht initialisiert wurde, wird nur Gruppeneigenschaften **DBPROPSET\_DBINIT** zurück.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBPropertiesImpl\-Klasse](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)