---
title: IRowsetLocateImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetLocateImpl
dev_langs: C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff76d78cd3f624e3bdb0d21af550a340a2aa498e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl-Klasse
Implementiert die OLE DB- [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) -Schnittstelle, die beliebige Zeilen aus einem Rowset abruft.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse `IRowsetLocateImpl`.  
  
 `RowsetInterface`  
 Eine abgeleitete Klasse `IRowsetImpl`.  
  
 `RowClass`  
 Die Einheit für die Speicherung der **HROW**.  
  
 `MapClass`  
 Für alle Zeilenhandles, die vom Anbieter Storage-Einheit.  
  
 `BookmarkKeyType`  
 Der Typ des Lesezeichens, z. B. einen Long-Wert oder eine Zeichenfolge. Gewöhnliche Lesezeichen müssen eine Länge von mindestens zwei Bytes haben. (Single-Byte-Länge ist für den OLE DB-reserviert [standard Lesezeichen](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK_FIRST**, **DBBMK_LAST**, und **DBBMK_INVALID**.)  
  
 `BookmarkType`  
 Die Zuordnungsmechanismus zum Verwalten von Lesezeichen datenbeziehungen.  
  
 `BookmarkMapClass`  
 Für alle Zeilenhandles, die vom Lesezeichen Storage-Einheit.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|Vergleicht zwei Lesezeichen.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Ruft die Zeilen, die die angegebenen Lesezeichen entsprechen ab.|  
|[Hash](../../data/oledb/irowsetlocateimpl-hash.md)|Gibt Hashing Werte für die angegebene Lesezeichen ausführen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|Ein Array von Lesezeichen.|  
  
## <a name="remarks"></a>Hinweise  
 `IRowsetLocateImpl`ist die OLE DB-Vorlagen-Implementierung von der [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) Schnittstelle. `IRowsetLocate`wird verwendet, um beliebige Zeilen aus einem Rowset abzurufen. Ein Rowset, das diese Schnittstelle nicht implementiert ist eine `sequential` Rowset. Wenn `IRowsetLocate` vorhanden ist für ein Rowset Spalte 0 ist das Lesezeichen für die Zeilen, lesen diese Spalte erhält einen Lesezeichenwert, der verwendet werden kann, um auf die gleiche Zeile neu zu positionieren.  
  
 `IRowsetLocateImpl`wird verwendet, um lesezeichenunterstützung in Anbietern zu implementieren. Lesezeichen sind Platzhalter (Indizes für ein Rowset), mit die den Consumer einer Zeile zurückkehren können Hochgeschwindigkeits-Zugriffe auf Daten. Der Anbieter bestimmt, welche Lesezeichen eindeutig können eine Zeile zu identifizieren. Mithilfe von `IRowsetLocateImpl` Methoden, Sie können Lesezeichen vergleichen, Fetch Zeilen durch Werte für offset, Fetch Zeilen von Lesezeichen und Hashwerte für Lesezeichen zurückzugeben.  
  
 Stellen Sie zur Unterstützung von OLE DB-Lesezeichen in einem Rowset, das Rowset, das von dieser Klasse erben.  
  
 Weitere Informationen zum Implementieren von Lesezeichen unterstützt, finden Sie unter [Anbieter unterstützt Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md) in der *Visual C++ Handbuch für Programmierer* und [Lesezeichen](https://msdn.microsoft.com/en-us/library/ms709728.aspx) in der *OLE DB Programmer's Reference* im Platform SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: "Atldb.h"  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md)   
 [BTextmarken](https://msdn.microsoft.com/en-us/library/ms709728.aspx)