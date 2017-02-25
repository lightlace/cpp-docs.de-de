---
title: "IRowsetCreatorImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetCreatorImpl"
  - "ATL.IRowsetCreatorImpl"
  - "ATL::IRowsetCreatorImpl<T>"
  - "ATL.IRowsetCreatorImpl<T>"
  - "IRowsetCreatorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetCreatorImpl-Klasse"
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IRowsetCreatorImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nimmt, erfüllt die gleichen Aufgaben wie `IObjectWithSite` können jedoch auch die OLE DB\-Eigenschaften **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## Syntax  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### Parameter  
 `T`  
 Eine Klasse von **IRowsetCreator** abgeleitet.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Legt die Website fest, die das Rowsetobjekt enthält.|  
  
## Hinweise  
 Diese Klasse erbt von [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) und überschreibt [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  Wenn ein Anbieterbefehl oder \-Sitzungsobjekt ein Rowset erstellt, wird `QueryInterface` für das Rowsetobjekt auf, das Sie nach `IObjectWithSite` gesucht und ruft `SetSite` auf, das die Schnittstelle **IUnkown** des Rowsetobjekts während die Siteschnittstelle übergibt.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)