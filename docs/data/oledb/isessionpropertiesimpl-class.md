---
title: "ISessionPropertiesImpl-Klasse"
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
  - "ISessionPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISessionPropertiesImpl-Klasse"
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ISessionPropertiesImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `ISessionPropertiesImpl` abgeleitet.  
  
 `PropClass`  
 Eine benutzerdefinierbaren diese Eigenschaftenklasse führt in `T`.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Gibt die Liste der Eigenschaften in der Sitzungseigenschaftengruppe zurück, die derzeit auf die Sitzung festgelegt werden.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Legt Eigenschaften in der Sitzungseigenschaftengruppe fest.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Sitzungen.  Diese Klasse implementiert Sitzungseigenschaften, indem eine statische Funktion definiert durch [Eigenschaftensetzuordnung](../../data/oledb/begin-propset-map.md) aufgerufen wird.  Die Eigenschaftensetzuordnung sollte in der Sitzungsklasse angegeben werden.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)