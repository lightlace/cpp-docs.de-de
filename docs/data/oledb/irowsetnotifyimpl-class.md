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
ms.openlocfilehash: f75f2cc2191fdaf2007d2c9a89544f917ccdcdd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506339"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl-Klasse

Implementiert und registriert [IRowsetNotify](/previous-versions/windows/desktop/ms712959) vom Consumer (auch bekannt als "Senke" genannt), damit Benachrichtigungen verarbeitet werden können.

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

`IRowsetNotifyImpl` bietet eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden [OnFieldChange](/previous-versions/windows/desktop/ms715961), [OnRowChange](/previous-versions/windows/desktop/ms722694), und [OnRowsetChange](/previous-versions/windows/desktop/ms722669). Wenn Sie von dieser Klasse erben, bei der Implementierung einer `IRowsetNotify` -Schnittstelle können Sie nur die benötigten Methoden implementieren. Sie müssen auch leere Implementierungen für die anderen Methoden selbst bereitstellen.

## <a name="onfieldchange"></a> IRowsetNotifyImpl:: Onfieldchange

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

Finden Sie unter [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="onrowchange"></a> IRowsetNotifyImpl:: Onrowchange

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

Finden Sie unter [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="onrowsetchange"></a> IRowsetNotifyImpl:: Onrowsetchange

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

Finden Sie unter [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) für parameterbeschreibungen.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) Beschreibungen von Wert zurückgeben.

### <a name="remarks"></a>Hinweise

Diese Methode umschließt die [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669) Methode. Beschreibung finden Sie diese Methode in der OLE DB Programmer's Reference Details.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959)
[IRowsetNotifyCP-Klasse](../../data/oledb/irowsetnotifycp-class.md)