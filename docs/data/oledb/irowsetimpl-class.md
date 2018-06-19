---
title: IRowsetImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetImpl class
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ca6d35eeea1dbfae4f2a5bb1b2ee93553e53519
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108437"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl-Klasse
Stellt eine Implementierung der `IRowset`-Schnittstelle bereit.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*>>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IRowsetImpl`.  
  
 `RowsetInterface`  
 Eine abgeleitete Klasse `IRowsetImpl`.  
  
 `RowClass`  
 Storage-Einheit für die **HROW**.  
  
 `MapClass`  
 Storage-Einheit für alle Zeilenhandles, die vom Anbieter.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|Fügt einen Verweiszähler für eine vorhandene Zeilenhandle an.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Wird aufgerufen, indem [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) Zuweisen einer neuen **HROW**. Nicht direkt vom Benutzer aufgerufen.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|Ruft Daten aus dem Rowset Kopie der Zeile ab.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Gibt den Status für das angegebene Feld zurück.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|Ruft Zeilen ab sequenziell, zum Speichern der vorherigen Position.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|Der Konstruktor. Nicht direkt vom Benutzer aufgerufen.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Wird aufgerufen, indem [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Nicht direkt vom Benutzer aufgerufen.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|Gibt Zeilen frei.|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Positioniert die nächste Abrufposition auf seine anfängliche Position; erstellt, d. h. seine Position, die bei der Erstinstallation des Rowsets.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Legt fest, der die Statusflags für das angegebene Feld.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Gibt an, ob ein Anbieter rückwärts abrufen unterstützt.|  
|[m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Gibt an, ob ein Anbieter die Cursor einen Bildlauf rückwärts aufweisen kann.|  
|[m_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Gibt an, ob ein Anbieter die Cursorposition zurückgesetzt wurde. Dies hat eine besondere Bedeutung, die beim Durchführen eines Bildlaufs Abwärtskompatibilität oder Abrufen von Abwärtskompatibilität in [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|Ein Index, der das Rowset, das den Cursor darstellt.|  
|[m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|Eine Liste von Zeilenhandles.|  
  
## <a name="remarks"></a>Hinweise  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) ist die grundlegende Rowset-Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)