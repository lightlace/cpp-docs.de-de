---
title: "IDBCreateSessionImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBCreateSessionImpl"
  - "ATL.IDBCreateSessionImpl"
  - "ATL::IDBCreateSessionImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBCreateSessionImpl-Klasse"
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBCreateSessionImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung für die [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
#### Parameter  
 `T`  
 IHRE CLASS\-Attribut, ABGELEITET OF  
  
 `SessionClass`  
 Das Sitzungsobjekt.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[CreateSession](../../data/oledb/idbcreatesessionimpl-createsession.md)|Erstellt eine neue Sitzung vom Datenquellenobjekt und die angeforderte Schnittstelle der neu erstellten Sitzung zurückkehren.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Datenquellenobjekte.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)