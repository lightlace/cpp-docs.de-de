---
title: "IOpenRowsetImpl-Klasse"
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
  - "IOpenRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOpenRowsetImpl-Klasse"
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IOpenRowsetImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Implementierung für die `IOpenRowset`\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### Parameter  
 `SessionClass`  
 Die Klasse, von `IOpenRowsetImpl` abgeleitet.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Erstellt ein Rowsetobjekt.  Wird nicht direkt nach Benutzer.|  
|["OpenRowset"](../../data/oledb/iopenrowsetimpl-openrowset.md)|Öffnet und gibt ein Rowset zurückgegeben, das sämtliche Zeilen aus einer einzelnen Basistabelle oder einem Index enthält. \(Nicht in ATLDB.H\)|  
  
## Hinweise  
 Die [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx)\-Schnittstelle ist für Sitzungsobjekte erforderlich.  Sie wird und gibt ein Rowset zurückgegeben, das sämtliche Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)