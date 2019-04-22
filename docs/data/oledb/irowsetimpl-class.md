---
title: IRowsetImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
ms.openlocfilehash: 47b03a542933c6223e098bc9d8fa8d45bf5e047b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024451"
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

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IRowsetImpl`.

*RowsetInterface*<br/>
Eine abgeleitete Klasse `IRowsetImpl`.

*RowClass*<br/>
Storage-Einheit für die `HROW`.

*MapClass*<br/>
Storage-Einheit für alle Zeilenhandles, die vom Anbieter.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[AddRefRows](#addrefrows)|Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.|
|[CreateRow](#createrow)|Wird aufgerufen, indem [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) Zuweisen einer neuen `HROW`. Nicht direkt vom Benutzer aufgerufen.|
|[GetData](#getdata)|Ruft Daten aus der Zeile des Rowsets ab.|
|[GetDBStatus](#getdbstatus)|Gibt den Status für das angegebene Feld zurück.|
|[GetNextRows](#getnextrows)|Ruft Zeilen sequenziell ab, speichert die vorherige Position.|
|[IRowsetImpl](#irowsetimpl)|Der Konstruktor. Nicht direkt vom Benutzer aufgerufen.|
|[RefRows](#refrows)|Wird aufgerufen, indem [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Nicht direkt vom Benutzer aufgerufen.|
|[ReleaseRows](#releaserows)|Gibt Zeilen frei.|
|[RestartPosition](#restartposition)|Automatisch neu positioniert und in die nächste Abrufposition auf seine anfängliche Position; Das heißt, erstellt die Position, an der das Rowset wurde.|
|[SetDBStatus](#setdbstatus)|Legt die Statusflags für das angegebene Feld.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|Gibt an, ob ein Anbieter Abrufen der Abwärtskompatibilität unterstützt.|
|[m_bCanScrollBack](#bcanscrollback)|Gibt an, ob ein Anbieter die Cursor Bildlauf rückwärts aufweisen kann.|
|[m_bReset](#breset)|Gibt an, ob ein Anbieter die Cursorposition zurückgesetzt wurde. Dies hat eine besondere Bedeutung beim Bildlauf rückwärts oder Abrufen von Abwärtskompatibilität in [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|
|[m_iRowset](#irowset)|Ein Index in das Rowset, der den Cursor darstellt.|
|[m_rgRowHandles](#rgrowhandles)|Eine Liste von Zeilenhandles.|

## <a name="remarks"></a>Hinweise

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) ist die grundlegende Rowset-Schnittstelle.

## <a name="addrefrows"></a> IRowsetImpl::AddRefRows

Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="createrow"></a> IRowsetImpl::CreateRow

Eine Hilfsmethode wird aufgerufen, indem [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) Zuweisen einer neuen `HROW`.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>Parameter

*lRowsOffset*<br/>
Cursorposition der Zeile erstellt wird.

*cRowsObtained*<br/>
Ein Verweis übergeben an den Benutzer, der angibt, der Anzahl der Zeilen, die erstellt werden.

*rgRows*<br/>
Ein Array von `HROW`s zurückgegeben, an den Aufrufer mit der neu erstellten Zeile behandelt.

### <a name="remarks"></a>Hinweise

Wenn die Zeile vorhanden ist, ruft diese Methode [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und zurückgibt. Andernfalls weist eine neue Instanz der Vorlagenvariable RowClass und fügt es [M_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).

## <a name="getdata"></a> IRowsetImpl::GetData

Ruft Daten aus der Zeile des Rowsets ab.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) in die *OLE DB-Programmierreferenz*.

Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IRowset::GetData`:

|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>Hinweise

Außerdem behandelt Datenkonvertierung bei Verwenden der OLE DB-Datenkonvertierung DLL.

## <a name="getdbstatus"></a> IRowsetImpl::GetDBStatus

Gibt die DBSTATUS Gleitkommaausnahme-Flags für das angegebene Feld zurück.

### <a name="syntax"></a>Syntax

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>Parameter

*currentRow*<br/>
[in] Die aktuelle Zeile.

*columnNames*<br/>
[in] Die Spalte, für die Status angefordert wird.

### <a name="return-value"></a>Rückgabewert

Die [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) Flags für die Spalte.

## <a name="getnextrows"></a> IRowsetImpl::GetNextRows

Ruft Zeilen sequenziell ab, speichert die vorherige Position.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset:: GetNextRows](/previous-versions/windows/desktop/ms709827(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="irowsetimpl"></a> IRowsetImpl::IRowsetImpl

Der Konstruktor.

### <a name="syntax"></a>Syntax

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>Hinweise

Sie müssen Allgemeinen nicht, diese Methode direkt aufzurufen.

## <a name="refrows"></a> IRowsetImpl::RefRows

Wird aufgerufen, indem [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) zu erhöhen, oder einen Verweiszähler auf einem vorhandenen Zeilenhandle freizugeben.

### <a name="syntax"></a>Syntax

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

## <a name="releaserows"></a> IRowsetImpl::ReleaseRows

Gibt Zeilen frei.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="restartposition"></a> IRowsetImpl::RestartPosition

Automatisch neu positioniert und in die nächste Abrufposition auf seine anfängliche Position; Das heißt, erstellt die Position, an der das Rowset wurde.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowset:: RestartPosition](/previous-versions/windows/desktop/ms712877(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Rowsetposition ist nicht definiert, bis `GetNextRow` aufgerufen wird. Können Sie rückwärts im Verschieben einer Rowet durch Aufrufen von `RestartPosition` , und klicken Sie dann Rückwärtsbildlauf oder-Abruf rückwärts.

## <a name="setdbstatus"></a> IRowsetImpl::SetDBStatus

Legt die DBSTATUS-Status-Flags für das angegebene Feld.

### <a name="syntax"></a>Syntax

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>Parameter

*statusFlags*<br/>
Die [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) Flags, die für die Spalte festgelegt.

*currentRow*<br/>
Die aktuelle Zeile.

*columnInfo*<br/>
Die Spalte, deren Status festgelegt wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Der Anbieter, überschreibt dieser Funktion können Sie speziellen Verarbeitung für DBSTATUS_S_ISNULL und DBSTATUS_S_DEFAULT bereitzustellen.

## <a name="bcanfetchback"></a> IRowsetImpl::m_bCanFetchBack

Gibt an, ob ein Anbieter Abrufen der Abwärtskompatibilität unterstützt.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>Hinweise

Verknüpft mit der `DBPROP_CANFETCHBACKWARDS` -Eigenschaft in der `DBPROPSET_ROWSET` Gruppe. Der Anbieter muss unterstützen `DBPROP_CANFETCHBACKWARDS` für `m_bCanFetchBackwards` sein **"true"**.

## <a name="bcanscrollback"></a> IRowsetImpl::m_bCanScrollBack

Gibt an, ob ein Anbieter die Cursor Bildlauf rückwärts aufweisen kann.

### <a name="syntax"></a>Syntax

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>Hinweise

Verknüpft mit der `DBPROP_CANSCROLLBACKWARDS` -Eigenschaft in der `DBPROPSET_ROWSET` Gruppe. Der Anbieter muss unterstützen `DBPROP_CANSCROLLBACKWARDS` für `m_bCanFetchBackwards` sein **"true"**.

## <a name="breset"></a> IRowsetImpl::m_bReset

Ein Bitflag, das verwendet, um zu bestimmen, ob die Cursorposition im Rowset definiert ist.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>Hinweise

Wenn der Consumer ruft [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) mit einem negativen `lOffset` oder *cRows* und `m_bReset` ist "true" `GetNextRows` verschiebt an das Ende des Rowsets. Wenn `m_bReset` ist "false", der Consumer erhält einen Fehlercode und in Übereinstimmung mit der OLE DB-Spezifikation. Die `m_bReset` Ruft ein Flag festgelegt, um **"true"** Wenn das Rowset zuerst erstellt wird und wenn der Consumer ruft [IRowsetImpl:: RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Ruft festgelegt ist, dass **"false"** beim Aufruf `GetNextRows`.

## <a name="irowset"></a> IRowsetImpl::m_iRowset

Ein Index in das Rowset, der den Cursor darstellt.

### <a name="syntax"></a>Syntax

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="rgrowhandles"></a> IRowsetImpl::m_rgRowHandles

Eine Zuordnung von Zeilenhandles, die derzeit vom Anbieter als Reaktion auf enthalten `GetNextRows`.

### <a name="syntax"></a>Syntax

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>Hinweise

Zeilenhandles werden entfernt, durch den Aufruf `ReleaseRows`. Finden Sie unter den [IRowsetImpl Übersicht](../../data/oledb/irowsetimpl-class.md) für die Definition von *MapClass*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow-Klasse](../../data/oledb/csimplerow-class.md)