---
title: "IRowsetImpl-Klasse"
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
  - "IRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetImpl-Klasse"
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der `IRowset`\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*   
   >  
>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IRowsetImpl` abgeleitet.  
  
 `RowsetInterface`  
 Eine Klasse wird von `IRowsetImpl` abgeleitet.  
  
 `RowClass`  
 Speichereinheit für **HROW**.  
  
 `MapClass`  
 Speichereinheit für alle Zeilenhandles angehalten vom Anbieter.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Wird von [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md), um neuen **HROW** zuzuordnen.  Wird nicht direkt nach Benutzer.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|Ruft Daten von der Zeilenkopie des Rowsets ab.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Gibt den Status für das angegebene Feld zurück.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|Ruft Zeilen sequenziell ab und speichert die vorherige Position.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|Der \-Konstruktor.  Wird nicht direkt nach Benutzer.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Wird von [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md).  Wird nicht direkt nach Benutzer.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|Gibt Zeilen frei.|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Ordnet die folgenden Abrufposition an seine Ausgangsposition neu an; das heißt, die Position, als das Rowset zuerst erstellt wurde.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Legt die Statusflags für das angegebene Feld.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Gibt an, ob ein Anbieter rückwärts abrufen unterstützt.|  
|[m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Gibt an, ob ein Anbieter den Cursor rückwärts scrollen werden kann.|  
|[m\_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Gibt an, ob ein Anbieter die Cursorposition zurückgesetzt wurde.  Dies hat eine besondere Bedeutung, wenn rückwärts durch Scrollen oder rückwärts in [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) abgerufen werden.|  
|[m\_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|Ein Index Rowset\-, den Cursor darstellt.|  
|[m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|Eine Liste der Zeilenhandles.|  
  
## Hinweise  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) ist die Basisklasse Rowsetschnittstelle.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)