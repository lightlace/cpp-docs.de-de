---
title: IRowsetLocateImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
dev_langs:
- C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 35ebe1a4534fa1c3a738d84e3e6dd7037254fd49
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059401"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl-Klasse

Implementiert die OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190) -Schnittstelle, die beliebige Zeilen aus einem Rowset abruft.

## <a name="syntax"></a>Syntax

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,
   class BookmarkKeyType = LONG,
   class BookmarkType = LONG,
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<
       T,
       RowsetInterface,
       RowClass,
       MapClass>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse `IRowsetLocateImpl`.

*RowsetInterface*<br/>
Eine abgeleitete Klasse `IRowsetImpl`.

*RowClass*<br/>
Die Storage-Einheit für die `HROW`.

*MapClass*<br/>
Die Storage-Einheit für alle Zeilenhandles, die vom Anbieter.

*BookmarkKeyType*<br/>
Der Typ der Wiederaufnahme des Lesezeichens, z. B. einen Long-Wert oder eine Zeichenfolge. Normale Lesezeichen müssen eine Länge von mindestens zwei Bytes. (Single-Byte-Länge ist für den OLE DB reserviert [standard Lesezeichen](/previous-versions/windows/desktop/ms712954)`DBBMK_FIRST`, `DBBMK_LAST`, und `DBBMK_INVALID`.)

*BookmarkType*<br/>
Der Zuordnungsmechanismus für die Verwaltung von Lesezeichen-to-Data-Beziehungen.

*BookmarkMapClass*<br/>
Die Storage-Einheit für alle Zeilenhandles, die vom Lesezeichen.

## <a name="requirements"></a>Anforderungen

**Header**: atldb.h

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[Compare](#compare)|Vergleicht zwei Lesezeichen.|
|[GetRowsAt](#getrowsat)|Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.|
|[GetRowsByBookmark](#getrowsbybookmark)|Ruft die Zeilen, die die angegebenen Lesezeichen entsprechen.|
|[Hash](#hash)|Gibt hash-Werte für den angegebenen Lesezeichen.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|Ein Array von Lesezeichen.|

## <a name="remarks"></a>Hinweise

`IRowsetLocateImpl` ist die Implementierung der OLE DB-Vorlagen von den [IRowsetLocate](/previous-versions/windows/desktop/ms721190) Schnittstelle. `IRowsetLocate` wird verwendet, um beliebige Zeilen aus einem Rowset abzurufen. Ein Rowset, das diese Schnittstelle nicht implementiert ist eine `sequential` Rowset. Wenn `IRowsetLocate` vorhanden ist für ein Rowset, ist die Spalte 0 das Lesezeichen für die Zeilen, lesen diese Spalte erhält einen Lesezeichenwert, der mit dem in der gleichen Zeile positioniert werden kann.

`IRowsetLocateImpl` wird verwendet, um lesezeichenunterstützung in Anbietern zu implementieren. Lesezeichen sind Platzhalter (Indizes für ein Rowset), mit die den Consumer schnell zu einer Zeile zurückkehren können schnelle Zugriff auf Daten gewährt. Der Anbieter bestimmt, wie Lesezeichen eindeutig können eine Zeile zu identifizieren. Mithilfe von `IRowsetLocateImpl` Methoden, Sie können Lesezeichen vergleichen, Fetch Zeilen durch die Werte für offset, Fetch-Zeilen durch Lesezeichen, und der Hashwerte für Lesezeichen zurückzugeben.

Stellen Sie zur Unterstützung von OLE DB-Lesezeichen in einem Rowset, das Rowset, das von dieser Klasse erben.

Informationen zum Implementieren der lesezeichenunterstützung finden Sie unter [-Anbieter unterstützt Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md) in die *Visual C++ Handbuch für Programmierer* und [Lesezeichen](/previous-versions/windows/desktop/ms709728) in die *OLE DB-Programmierreferenz* im Platform SDK.

## <a name="compare"></a> IRowsetLocateImpl:: Compare

Vergleicht zwei Lesezeichen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetLocate::Compare](/previous-versions/windows/desktop/ms709539) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Eine der Lesezeichen können ein Standard werden OLE DB-definierten [standard Lesezeichen](/previous-versions/windows/desktop/ms712954) (`DBBMK_FIRST`, `DBBMK_LAST`, oder `DBBMK_INVALID`). Der zurückgegebene Wert in `pComparison` gibt die Beziehung zwischen zwei Lesezeichen:

- DBCOMPARE_LT (`cbBookmark1` ist, bevor Sie `cbBookmark2`.)

- DBCOMPARE_EQ (`cbBookmark1` gleich `cbBookmark2`.)

- DBCOMPARE_GT (`cbBookmark1` ist nach `cbBookmark2`.)

- DBCOMPARE_NE (Lesezeichen sind gleich und nicht sortiert.)

- DBCOMPARE_NOTCOMPARABLE (Lesezeichen können nicht verglichen werden.)

## <a name="getrowsat"></a> IRowsetLocateImpl:: GetRowsAt

Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetLocate:: GetRowsAt](/previous-versions/windows/desktop/ms723031) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Um stattdessen von der Cursorposition bis zu abzurufen, verwenden Sie [IRowset::GetRowsAt](/previous-versions/windows/desktop/ms723031).

`IRowsetLocateImpl::GetRowsAt` die Position des Cursors wird nicht geändert werden.

## <a name="getrowsbybookmark"></a> IRowsetLocateImpl:: Getrowsbybookmark

Ruft eine oder mehrere Zeilen, die die angegebenen Lesezeichen entsprechen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>Parameter

*hReserved*<br/>
[in] Entspricht *hChapter* Parameter [IRowsetLocate:: Getrowsbybookmark](/previous-versions/windows/desktop/ms725420).

Andere Parameter, finden Sie unter [IRowsetLocate:: Getrowsbybookmark](/previous-versions/windows/desktop/ms725420) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Das Lesezeichen kann ein Wert, die Sie definieren oder eine OLE DB sein [standard Lesezeichen](/previous-versions/windows/desktop/ms712954) (`DBBMK_FIRST` oder `DBBMK_LAST`). die Position des Cursors wird nicht geändert werden.

## <a name="hash"></a> IRowsetLocateImpl:: Hash

Gibt hash-Werte für den angegebenen Lesezeichen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>Parameter

*hReserved*<br/>
[in] Entspricht *hChapter* Parameter [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697).

Andere Parameter, finden Sie unter [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697) in die *OLE DB-Programmierreferenz*.

## <a name="rgbookmarks"></a> IRowsetLocateImpl:: M_rgbookmarks

Ein Array von Lesezeichen.

### <a name="syntax"></a>Syntax

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate:IRowset](/previous-versions/windows/desktop/ms721190)
[Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[BTextmarken](/previous-versions/windows/desktop/ms709728)