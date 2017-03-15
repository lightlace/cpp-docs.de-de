---
title: "IRowsetLocateImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetLocateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lesezeichen, OLE DB"
  - "IRowsetLocateImpl-Klasse"
  - "Anbieter, Lesezeichen"
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# IRowsetLocateImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die OLE DB\- [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)\-Schnittstelle, die beliebige Zeilen aus einem Rowset abgerufen werden.  
  
## Syntax  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### Parameter  
 `T`  
 Eine Klasse wird von `IRowsetLocateImpl` abgeleitet.  
  
 `RowsetInterface`  
 Eine Klasse wird von `IRowsetImpl` abgeleitet.  
  
 `RowClass`  
 Die Speichereinheit für **HROW**.  
  
 `MapClass`  
 Die Speichereinheit für alle Zeilenhandles hielt vom Anbieter an.  
  
 `BookmarkKeyType`  
 Der Typ des Lesezeichens, wie LONG oder eine Zeichenfolge.  Gewöhnliche Lesezeichen müssen eine Länge von zwei Bytes mindestens haben. \(Einzelbytelänge wird für die OLE DB\- [Standardlesezeichen](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK\_FIRST**, **DBBMK\_LAST** und **DBBMK\_INVALID**.\) reserviert  
  
 `BookmarkType`  
 Der Zuordnungsmechanismus für Wartungslesezeichen\-zudatenbeziehungen.  
  
 `BookmarkMapClass`  
 Die Speichereinheit für alle Zeilenhandles hielt vom Lesezeichen an.  
  
## Member  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|Vergleicht zwei Lesezeichen.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Ruft das Zeilen Starten mit der Zeile, die durch einen UTC\-Offset von einem Lesezeichen angegeben wird.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Ruft die Zeilen, die die angegebenen Lesezeichen übereinstimmen.|  
|[Hash](../../data/oledb/irowsetlocateimpl-hash.md)|Gibt Hashwerten für die angegebenen Lesezeichen zurück.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|Ein Array Lesezeichen.|  
  
## Hinweise  
 `IRowsetLocateImpl` ist die OLE DB\-Vorlagen\-Implementierung der [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)\-Schnittstelle.  `IRowsetLocate` wird verwendet, um beliebige Zeilen aus einem Rowset abgerufen.  Ein Rowset, das diese Schnittstelle nicht implementiert, ist ein `sequential` Rowset.  Wenn `IRowsetLocate` für ein Rowset vorhanden ist, lautet Spalte 0 das Lesezeichen für die Linien; diese Spalte werden, erhält einen Lesezeichenwert, der verwendet werden kann, um zur gleichen Zeile neu anzuordnen.  
  
 `IRowsetLocateImpl` wird verwendet, um Unterstützung in den Anbieter zu implementieren.  Lesezeichen sind die Platzhalter \(Indizes für ein Rowset\) das den Consumer aktivieren, um in eine Zeile schnell zurückzukehren und ermöglichen Hochgeschwindigkeitszugriff an Daten.  Der Anbieter ermittelt, welche Lesezeichen eine Zeile eindeutig identifizieren können.  Mit `IRowsetLocateImpl` können Sie Methoden Lesezeichen vergleichen, Zeilen nach Offset abrufen, Zeilen durch Lesezeichen abrufen, und Hashwerten für Lesezeichen zurückgeben.  
  
 Um in OLE DB\-Lesezeichen einem Rowset zu unterstützen, führen Sie das Rowset erben von dieser Klasse.  
  
 Informationen zum Implementieren der Unterstützung, finden Sie unter [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md) und [Lesezeichen](https://msdn.microsoft.com/en-us/library/ms709728.aspx) in *Visual C\+\+ Programmer's Guide* in *OLE DB Programmer's Reference* in `Platform``SDK`.  
  
## Anforderungen  
 **Header**: atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md)   
 [Bookmarks](https://msdn.microsoft.com/en-us/library/ms709728.aspx)