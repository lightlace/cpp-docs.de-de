---
title: IRowsetNotifyImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
ms.openlocfilehash: 552fcdcee99f1bfe78a28c6ea41a89557f1682f4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026067"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl-Klasse

Implementiert und registriert [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) vom Consumer (auch bekannt als "Senke" genannt), damit Benachrichtigungen verarbeitet werden können.

## <a name="syntax"></a>Syntax

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[OnFieldChange](#onfieldchange)|Benachrichtigt den Consumer über alle Änderungen auf den Wert einer Spalte.|
|[OnRowChange](#onrowchange)|Benachrichtigt den Consumer über die erste Änderung an einer Zeile oder über jede Änderung, die die gesamte Zeile betroffen sind.|
|[OnRowsetChange](#onrowsetchange)|Benachrichtigt den Consumer über alle Änderungen, die Auswirkungen auf das gesamte Rowset.|

## <a name="remarks"></a>Hinweise

Finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) zur Implementierung der vom Consumer der Verbindungspunkt-Schnittstelle.

`IRowsetNotifyImpl` bietet eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden [OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)), [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)), und [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)). Wenn Sie von dieser Klasse erben, bei der Implementierung einer `IRowsetNotify` -Schnittstelle können Sie nur die benötigten Methoden implementieren. Sie müssen auch leere Implementierungen für die anderen Methoden selbst bereitstellen.

## <a name="onfieldchange"></a> IRowsetNotifyImpl::OnFieldChange

Benachrichtigt den Consumer über alle Änderungen auf den Wert einer Spalte.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(OnFieldChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ HROW /* hRow */,
/* [in] */ DBORDINAL /* cColumns */,
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="onrowchange"></a> IRowsetNotifyImpl::OnRowChange

Benachrichtigt den Consumer über die erste Änderung an einer Zeile oder über jede Änderung, die die gesamte Zeile betroffen sind.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(OnRowChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBCOUNTITEM /* cRows */,
/* [size_is][in] */ const HROW /* rghRows*/ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="onrowsetchange"></a> IRowsetNotifyImpl::OnRowsetChange

Benachrichtigt den Consumer über alle Änderungen, die Auswirkungen auf das gesamte Rowset.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))
[IRowsetNotifyCP-Klasse](../../data/oledb/irowsetnotifycp-class.md)