---
title: IRowsetChangeImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: 8b2a92fdefd965d4b87e0a9ed411cc1b5c89b8f9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036798"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl-Klasse

Die OLE DB-Vorlagen-Implementierung, der die [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) -Schnittstelle in der OLE DB-Spezifikation.

## <a name="syntax"></a>Syntax

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse `IRowsetChangeImpl`.

*Speicher*<br/>
Der Benutzerdatensatz.

*BaseInterface*<br/>
Die Basisklasse für die Schnittstelle, wie z. B. `IRowsetChange`.

*RowClass*<br/>
Die Storage-Einheit für das Zeilenhandle.

*MapClass*<br/>
Die Storage-Einheit für alle Zeilenhandles, die vom Anbieter.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods-used-with-irowsetchange"></a>Schnittstellenmethoden (mit IRowsetChange verwendet)

|||
|-|-|
|[DeleteRows](#deleterows)|Löscht Zeilen aus dem Rowset.|
|[InsertRow](#insertrow)|Fügt eine Zeile für das Rowset an.|
|[SetData](#setdata)|Legt Datenwerte in einer oder mehreren Spalten fest.|

### <a name="implementation-method-callback"></a>Die Implementierungsmethode (Rückruf)

|||
|-|-|
|[FlushData](#flushdata)|Außer Kraft gesetzt, vom Anbieter, um Daten in den Speicher zu übernehmen.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle ist verantwortlich für sofortige Schreibvorgänge in einem Datenspeicher. "Naheliegenden" bedeutet, dass wenn der Endbenutzer (die Person, die des Consumers) Änderungen sendet, diese Änderungen sofort an den Daten übertragen werden gespeichert und können nicht rückgängig gemacht.

`IRowsetChangeImpl` implementiert die OLE DB `IRowsetChange` -Schnittstelle, die ermöglicht, der Werte der Spalten in vorhandenen Zeilen löschen von Zeilen sowie das Einfügen neuer Zeilen aktualisiert.

Die OLE DB-Vorlagen-Implementierung unterstützt die Basismethoden (`SetData`, `InsertRow`, und `DeleteRows`).

> [!IMPORTANT]
>  Es wird dringend empfohlen, bevor Sie versuchen, Ihren Anbieter implementiert die folgende Dokumentation zu lesen:

- [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)

- Kapitel 6, der die *OLE DB-Programmierreferenz*

- Siehe auch die `RUpdateRowset` Klasse wird verwendet, der [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) Beispiel.

## <a name="deleterows"></a> IRowsetChangeImpl::DeleteRows

Löscht Zeilen aus dem Rowset.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetChange:: DeleteRows](/previous-versions/windows/desktop/ms724362(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="insertrow"></a> IRowsetChangeImpl::InsertRow

Erstellt und initialisiert eine neue Zeile im Rowset.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetChange:: InsertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="setdata"></a> IRowsetChangeImpl::SetData

Legt Datenwerte in einer oder mehreren Spalten fest.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="flushdata"></a> IRowsetChangeImpl::FlushData

Außer Kraft gesetzt, vom Anbieter, um Daten in den Speicher zu übernehmen.

### <a name="syntax"></a>Syntax

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Parameter

*hRowToFlush*<br/>
[in] Handle für die Zeilen für die Daten. Der Typ dieser Zeile wird bestimmt, von der *RowClass* -Vorlagenargument vom die `IRowsetImpl` Klasse (`CSimpleRow` standardmäßig).

*hAccessorToFlush*<br/>
[in] Handle für den Accessor wird das Binden von Informationen und Typinformationen im enthält die `PROVIDER_MAP` (finden Sie unter [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)