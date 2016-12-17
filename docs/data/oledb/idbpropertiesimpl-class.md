---
title: "IDBPropertiesImpl-Klasse"
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
  - "IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl"
  - "ATL.IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl<T>"
  - "ATL::IDBPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBPropertiesImpl-Klasse"
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IDBPropertiesImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung für die `IDBProperties`\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IDBPropertiesImpl` abgeleitet.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Gibt den Werten von Eigenschaften in die Datenquellen\-, Datenquellen\-Informationens\- und Initialisierungseigenschaftengruppen zurück, die gerade im Datenquellenobjekt oder die Werte von Eigenschaften in der Initialisierungseigenschaftengruppe festgelegt werden, die derzeit auf den Enumerator festgelegt werden.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Gibt Informationen zu allen Eigenschaften zurück, die vom Anbieter unterstützt werden.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Legt Eigenschaften in die Datenquellen\- und Initialisierungseigenschaftengruppen, für Datenquellenobjekte oder die Initialisierungseigenschaftengruppe, für Enumeratoren fest.|  
  
## Hinweise  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) ist eine erforderliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren.  Wenn ein Enumerator [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx) verfügbar macht, muss es `IDBProperties` verfügbar machen.  `IDBPropertiesImpl` implementiert `IDBProperties`, indem Sie eine statische Funktion, die durch [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md) definierten Reihenfolge.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)