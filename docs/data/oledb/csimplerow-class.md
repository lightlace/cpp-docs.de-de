---
title: CSimpleRow-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- CSimpleRow
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: 19b90f4454e784907366ef6cf7e3e7e1b9ada799
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023840"
---
# <a name="csimplerow-class"></a>CSimpleRow-Klasse

Stellt eine Standardimplementierung für den Zeilenziehpunkt, die in dient der [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) Klasse.

## <a name="syntax"></a>Syntax

```cpp
class CSimpleRow
```

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[AddRefRow](#addrefrow)|Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.|
|[Vergleichen](#compare)|Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.|
|[CSimpleRow](#csimplerow)|Der Konstruktor.|
|[ReleaseRow](#releaserow)|Gibt Zeilen frei.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_dwRef](#dwref)|Der Verweiszähler auf einem vorhandenen Zeilenhandle.|
|[m_iRowset](#irowset)|Ein Index in das Rowset, der den Cursor darstellt.|

## <a name="remarks"></a>Hinweise

Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile. `IRowsetImpl` erstellt ein neues `CSimpleRow` für jede Zeile im angeforderten [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` kann auch durch eine eigene Implementierung von den Zeilenziehpunkt, ersetzt werden, wie ein Standardvorlagenargument zu `IRowsetImpl`. Die einzige Voraussetzung für diese Klasse zu ersetzen ist, damit die äquivalente Klasse einen Konstruktor bereit, der einen einzelnen Parameter vom Typ akzeptiert **lange**.

## <a name="addrefrow"></a> CSimpleRow::AddRefRow

Fügt einen Verweiszähler auf einem vorhandenen Zeilenhandle auf threadsichere Weise.

### <a name="syntax"></a>Syntax

```cpp
DWORD AddRefRow();
```

## <a name="compare"></a> CSimpleRow::Compare

Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>Parameter

*pRow*<br/>
Ein Zeiger auf ein `CSimpleRow` -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Wert, in der Regel S_OK, der angibt, die zwei Zeilen sind die gleiche Zeileninstanz oder S_FALSE, der angibt, der zwei Zeilen sind unterschiedlich. Finden Sie unter [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) in die *OLE DB-Programmierreferenz* für weitere mögliche Rückgabewerte.

## <a name="csimplerow"></a> CSimpleRow::CSimpleRow

Der Konstruktor.

### <a name="syntax"></a>Syntax

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>Parameter

*iRowsetCur*<br/>
[in] Indizieren Sie auf das aktuelle Rowset.

### <a name="remarks"></a>Hinweise

Legt [M_iRowset](../../data/oledb/csimplerow-m-irowset.md) zu *iRowsetCur*.

## <a name="releaserow"></a> CSimpleRow::ReleaseRow

Gibt die Zeilen in einer threadsicheren Weise frei.

### <a name="syntax"></a>Syntax

```cpp
DWORD ReleaseRow();
```

## <a name="dwref"></a> CSimpleRow::m_dwRef

Der Verweiszähler auf einem vorhandenen Zeilenhandle.

### <a name="syntax"></a>Syntax

```cpp
DWORD m_dwRef;
```

## <a name="irowset"></a> CSimpleRow::m_iRowset

Indizieren Sie auf das Rowset, der den Cursor darstellt.

### <a name="syntax"></a>Syntax

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)