---
title: IOpenRowsetImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
ms.openlocfilehash: 3d4f778f560b55f22c1c54185bea79af07949ceb
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422751"
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl-Klasse

Stellt die Implementierung für die `IOpenRowset` Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class SessionClass>
class IOpenRowsetImpl : public IOpenRowset
```

### <a name="parameters"></a>Parameter

*SessionClass*<br/>
Abgeleitet von die Klasse `IOpenRowsetImpl`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CreateRowset](#createrowset)|Erstellt ein Rowsetobjekt. Nicht direkt vom Benutzer aufgerufen.|
|[OpenRowset](#openrowset)|Öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält. (Nicht im ATLDB. H)|

## <a name="remarks"></a>Hinweise

Die [IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85)) Schnittstelle ist erforderlich, damit ein Sitzungsobjekt. Es wird geöffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.

## <a name="createrowset"></a> IOpenRowsetImpl::CreateRowset

Erstellt ein Rowsetobjekt. Nicht direkt vom Benutzer aufgerufen. Finden Sie unter [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) in die *OLE DB-Programmierreferenz.*

### <a name="syntax"></a>Syntax

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>Parameter

*RowsetClass*<br/>
Ein Member von Vorlage-Klasse, die Rowset-Klasse für den Benutzer darstellt. In der Regel vom Assistenten generiert.

*pRowsetObj*<br/>
[out] Ein Zeiger auf eine Rowset-Objekt. Dieser Parameter wird in der Regel nicht verwendet, aber es kann verwendet werden, wenn Sie mehr Arbeit für das Rowset ausführen müssen, vor der Übergabe an ein COM-Objekt. Die Lebensdauer des *pRowsetObj* gebunden ist, indem *PpRowset*.

Andere Parameter, finden Sie unter [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) in die *OLE DB-Programmiererreferenz.*

## <a name="openrowset"></a> IOpenRowsetImpl::OpenRowset

Öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.

### <a name="syntax"></a>Syntax

```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,
   DBID* pTableID,
   DBID* pIndexID,
   REFIID riid,
   ULONG cPropertySets,
   DBPROPSET rgPropertySets[],
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IOpenRowset:: OPENROWSET](/previous-versions/windows/desktop/ms716724(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Diese Methode wird in ATLDB nicht gefunden. H. Sie wird von ATL-Objektassistenten erstellt, wenn Sie einen Anbieter erstellen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)