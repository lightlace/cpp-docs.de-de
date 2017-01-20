---
title: "ICommandPropertiesImpl-Klasse"
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
  - "ICommandPropertiesImpl"
  - "ATL.ICommandPropertiesImpl"
  - "ATL::ICommandPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandPropertiesImpl-Klasse"
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandPropertiesImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### Parameter  
 `T`  
 Ihre Klasse, abgeleitet von  
  
 `PropClass`  
 der Eigenschaftenklasse.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Gibt die Liste der Eigenschaften in der Rowseteigenschaftengruppe zurück, die nur das Rowset angefordert werden.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Legt Eigenschaften in der Rowseteigenschaftengruppe fest.|  
  
## Hinweise  
 Dies ist auf Befehlen erforderlich.  Die Implementierung von einer statischen Funktion bereitgestellt, die vom [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md)\-Makro definiert wird.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)