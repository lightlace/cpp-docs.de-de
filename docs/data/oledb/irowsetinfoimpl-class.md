---
title: "IRowsetInfoImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetInfoImpl"
  - "IRowsetInfoImpl"
  - "ATL::IRowsetInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetInfoImpl-Klasse"
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetInfoImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung für die [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IRowsetInfoImpl` abgeleitet.  
  
 `PropClass`  
 Eine benutzerdefinierbaren diese Eigenschaftenklasse führt in `T`.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|Gibt die aktuellen Einstellungen aller vom Rowset unterstützten Eigenschaften zurück.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Gibt einen Schnittstellenzeiger Rowset\- zurück, auf das ein Lesezeichen gilt.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|Gibt einen Schnittstellenzeiger auf das Objekt \(Befehl oder Sitzung\) zurück, das dieses Rowset erstellt hat.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Rowsets.  Diese Klasse implementiert die Rowseteigenschaften, indem Sie die [Eigenschaftensetzuordnung](../../data/oledb/begin-propset-map.md) verwenden, das in der Befehlsklasse definiert wird.  Obwohl die Rowsetklasse angezeigt, die sich der Befehlsklassen zu verwenden, wird das Rowset mit einer eigenen Kopie der Laufzeiteigenschaften angegeben, wenn er von einem Befehl oder ein Sitzungsobjekt erstellt wird.  
  
## Anforderungen  
 **Header:**  altdb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)