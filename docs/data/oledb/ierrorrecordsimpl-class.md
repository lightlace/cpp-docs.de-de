---
title: IErrorRecordsImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
- GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpContext
- IErrorRecordsImpl.GetErrorHelpContext
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
- IErrorRecordsImpl::GetErrorParameters
- ATL.IErrorRecordsImpl.GetErrorParameters
- IErrorRecordsImpl.GetErrorParameters
- GetErrorParameters
- ATL::IErrorRecordsImpl::GetErrorParameters
- IErrorRecordsImpl::GetRecordCount
- ATL::IErrorRecordsImpl::GetRecordCount
- IErrorRecordsImpl.GetRecordCount
- ATL.IErrorRecordsImpl.GetRecordCount
- IErrorRecordsImpl::m_rgErrors
- IErrorRecordsImpl.m_rgErrors
- ATL.IErrorRecordsImpl.m_rgErrors
- m_rgErrors
- ATL::IErrorRecordsImpl::m_rgErrors
helpviewer_keywords:
- IErrorRecordsImpl class
- GetErrorDescriptionString method
- GetErrorGUID method
- GetErrorHelpContext method
- GetErrorHelpFile method
- GetErrorSource method
- AddErrorRecord method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetRecordCount method
- m_rgErrors
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
ms.openlocfilehash: b1ab6b0984cbf84690d69a3ffe7eb3931bf59563
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029472"
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl-Klasse

Implementiert die OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) Schnittstelle, Hinzufügen von Einträgen zu und Abrufen von Datensätzen aus einem Datenmember ([M_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) vom Typ **CAtlArray <** `RecordClass`**>**.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class RecordClass = ATLERRORINFO>
class IErrorRecordsImpl : public IErrorRecords
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse `IErrorRecordsImpl`.

*RecordClass*<br/>
Eine Klasse, die ein OLE DB-Error-Objekt darstellt.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetErrorDescriptionString](#geterrordescriptionstring)|Ruft die Zeichenfolge zur fehlerbeschreibung aus einen Fehlerdatensatz ab.|
|[GetErrorGUID](#geterrorguid)|Ruft den GUID-Fehler aus einen Fehlerdatensatz ab.|
|[GetErrorHelpContext](#geterrorhelpcontext)|Ruft die Hilfekontext-ID aus einen Fehlerdatensatz ab.|
|[GetErrorHelpFile](#geterrorhelpfile)|Ruft den vollständigen Pfadnamen der Hilfedatei aus einen Fehlerdatensatz ab.|
|[GetErrorSource](#geterrorsource)|Ruft den Fehlercode für die Quelle über einen Fehlerdatensatz ab.|

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[AddErrorRecord](#adderrorrecord)|Fügt einen Datensatz auf den OLE DB-Error-Objekt.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurück.|
|[GetCustomErrorObject](#getcustomerrorobject)|Gibt einen Zeiger auf eine Schnittstelle für einen benutzerdefinierten Fehler-Objekt zurück.|
|[GetErrorInfo](#geterrorinfo)|Gibt eine [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) Schnittstellenzeiger auf den angegebenen Datensatz.|
|[GetErrorParameters](#geterrorparameters)|Gibt die Fehlerparameter zurück.|
|[GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in der OLE DB-Datensatz-Objekt zurück.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_rgErrors](#rgerrors)|Ein Array von fehlerdatensätzen.|

## <a name="geterrordescriptionstring"></a> IErrorRecordsImpl::GetErrorDescriptionString

Ruft die Zeichenfolge zur fehlerbeschreibung aus einen Fehlerdatensatz ab.

### <a name="syntax"></a>Syntax

```cpp
LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parameter

*rCurError*<br/>
Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Zeichenfolge, die den Fehler beschreibt.

## <a name="geterrorguid"></a> IErrorRecordsImpl::GetErrorGUID

Ruft den GUID-Fehler aus einen Fehlerdatensatz ab.

### <a name="syntax"></a>Syntax

```cpp
REFGUID GetErrorGUID(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parameter

*rCurError*<br/>
Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf eine GUID für den Fehler.

## <a name="geterrorhelpcontext"></a> IErrorRecordsImpl::GetErrorHelpContext

Ruft die Hilfekontext-ID aus einen Fehlerdatensatz ab.

### <a name="syntax"></a>Syntax

```cpp
DWORD GetErrorHelpContext(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parameter

*rCurError*<br/>
Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Die Hilfekontext-ID für den Fehler.

## <a name="geterrorhelpfile"></a> IErrorRecordsImpl::GetErrorHelpFile

Ruft den Pfadnamen der Hilfedatei aus einen Fehlerdatensatz ab.

### <a name="syntax"></a>Syntax

```cpp
LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parameter

*rCurError*<br/>
Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine Zeichenfolge, die den Pfadnamen der Hilfedatei für den Fehler enthält.

## <a name="geterrorsource"></a> IErrorRecordsImpl::GetErrorSource

Ruft den Quellcode, der den Fehler verursacht, über einen Fehlerdatensatz hat ab.

### <a name="syntax"></a>Syntax

```cpp
LPOLESTR GetErrorSource(ERRORINFO& rCurError);
```

#### <a name="parameters"></a>Parameter

*rCurError*<br/>
Ein `ERRORINFO` Datensatz in einer `IErrorInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine Zeichenfolge, die den Quellcode für den Fehler enthält.

## <a name="adderrorrecord"></a> IErrorRecordsImpl::AddErrorRecord

Fügt einen Datensatz auf den OLE DB-Error-Objekt.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,
   DWORD dwLookupID,
   DISPPARAMS *pdispparams,
   IUnknown *punkCustomError,
   DWORD dwDynamicErrorID);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::AddErrorRecord](/previous-versions/windows/desktop/ms725362(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="getbasicerrorinfo"></a> IErrorRecordsImpl::GetBasicErrorInfo

Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,
   ERRORINFO *pErrorInfo);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="getcustomerrorobject"></a> IErrorRecordsImpl::GetCustomErrorObject

Gibt einen Zeiger auf eine Schnittstelle für einen benutzerdefinierten Fehler-Objekt zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,
   REFIID riid,
   IUnknown **ppObject);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="geterrorinfo"></a> IErrorRecordsImpl::GetErrorInfo

Gibt eine [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) Schnittstellenzeiger auf den angegebenen Datensatz.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetErrorInfo )(ULONG ulRecordNum,
   LCID lcid,
   IErrorInfo **ppErrorInfo);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="geterrorparameters"></a> IErrorRecordsImpl::GetErrorParameters

Gibt die Fehlerparameter zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetErrorParameters )(ULONG ulRecordNum,
   DISPPARAMS *pdispparams);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="getrecordcount"></a> IErrorRecordsImpl::GetRecordCount

Gibt die Anzahl der Datensätze in der OLE DB-Datensatz-Objekt zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetRecordCount )(ULONG *pcRecords);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetRecordCount](/previous-versions/windows/desktop/ms722724(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="rgerrors"></a> IErrorRecordsImpl::m_rgErrors

Ein Array von fehlerdatensätzen.

### <a name="syntax"></a>Syntax

```cpp
CAtlArray< RecordClass > m_rgErrors;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)