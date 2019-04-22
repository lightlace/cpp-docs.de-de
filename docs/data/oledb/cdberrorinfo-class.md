---
title: CDBErrorInfo-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
- CDBErrorInfo::GetCustomErrorObject
- ATL.CDBErrorInfo.GetCustomErrorObject
- CDBErrorInfo.GetCustomErrorObject
- ATL::CDBErrorInfo::GetCustomErrorObject
- GetCustomErrorObject
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
- ATL.CDBErrorInfo.GetErrorParameters
- CDBErrorInfo::GetErrorParameters
- ATL::CDBErrorInfo::GetErrorParameters
- CDBErrorInfo.GetErrorParameters
- GetErrorParameters
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
helpviewer_keywords:
- CDBErrorInfo class
- GetAllErrorInfo method
- GetBasicErrorInfo method
- GetCustomErrorObject method
- GetErrorInfo method
- GetErrorParameters method
- GetErrorRecords method
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
ms.openlocfilehash: bc13137a4222ba51cf3745f9706353d48068a072
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021539"
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo-Klasse

Bietet Unterstützung für OLE DB-fehlerverarbeitung mit dem OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
class CDBErrorInfo
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetAllErrorInfo](#getallerrorinfo)|Gibt alle Fehlerinformationen, die innerhalb eines fehlerdatensatzes.|
|[GetBasicErrorInfo](#getbasicerrorinfo)|Aufrufe [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) grundlegende Informationen zu dem angegebenen Fehler zurückgegeben werden sollen.|
|[GetCustomErrorObject](#getcustomerrorobject)|Aufrufe [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) um einen Zeiger auf eine Schnittstelle für ein Objekt für die benutzerdefinierten Fehler zurückzugeben.|
|[GetErrorInfo](#geterrorinfo)|Aufrufe [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) zurückzugebenden ein `IErrorInfo` Schnittstellenzeiger auf den angegebenen Datensatz.|
|[GetErrorParameters](#geterrorparameters)|Aufrufe [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) die Fehlerparameter zurückgegeben.|
|[GetErrorRecords](#geterrorrecords)|Ruft die Error-Datensätze für das angegebene Objekt ab.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle gibt einen oder mehrere Error-Datensätze für den Benutzer zurück. Rufen Sie [cdberrorinfo:: Geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) zuerst, damit die Anzahl der Fehlerdatensätze zu erhalten. Dann eine der der Zugriff Funktionen, z. B. [cdberrorinfo:: Getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), um Fehlerinformationen für jeden Datensatz abzurufen.

## <a name="getallerrorinfo"></a> CDBErrorInfo::GetAllErrorInfo

Gibt alle Typen von Fehlerinformationen enthalten, die in einen Fehlerdatensatz zurück.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetAllErrorInfo(ULONG ulRecordNum,
   LCID lcid,  BSTR* pbstrDescription,
   BSTR* pbstrSource = NULL,
   GUID* pguid = NULL,
   DWORD* pdwHelpContext = NULL,
   BSTR* pbstrHelpFile = NULL) const throw();
```

#### <a name="parameters"></a>Parameter

*ulRecordNum*<br/>
[in] Die nullbasierte Nummer des Datensatzes für die Fehlerinformationen zurückgegeben werden sollen.

*lcid*<br/>
[in] Die Gebietsschema-ID für die Fehlerinformationen zurückgegeben werden.

*pbstrDescription*<br/>
[out] Ein Zeiger auf eine textbeschreibung des Fehlers oder NULL, wenn das Gebietsschema nicht unterstützt wird. Siehe Hinweise.

*pbstrSource*<br/>
[out] Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Komponente, die den Fehler generiert hat.

*pguid*<br/>
[out] Ein Zeiger auf die GUID der Schnittstelle, die den Fehler definiert.

*pdwHelpContext*<br/>
[out] Ein Zeiger auf die Hilfekontext-ID für den Fehler.

*pbstrHelpFile*<br/>
[out] Ein Zeiger auf eine Zeichenfolge, die mit dem Pfad zur Hilfedatei, die den Fehler beschreibt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich. Finden Sie unter [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) in die *OLE DB-Programmierreferenz* für andere Werte zurückgeben.

### <a name="remarks"></a>Hinweise

Der Ausgabewert des *PbstrDescription* wird intern durch den Aufruf abgerufen `IErrorInfo::GetDescription`, wodurch den Wert auf NULL festgelegt, wenn das Gebietsschema nicht unterstützt wird, oder wenn beide der folgenden Bedingungen zutreffen:

1. der Wert des *Lcid* ist nicht-US Englisch und

1. der Wert des *Lcid* ist nicht gleich dem Wert, der von GetUserDefaultLCID zurückgegeben.

## <a name="getbasicerrorinfo"></a> CDBErrorInfo::GetBasicErrorInfo

Aufrufe [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die Anzahl der Anbieter-spezifischer Fehler zurückgegeben werden sollen.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,
   ERRORINFO* pErrorInfo) const throw();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetBasicErrorInfo](/previous-versions/windows/desktop/ms723907(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="getcustomerrorobject"></a> CDBErrorInfo::GetCustomErrorObject

Aufrufe [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) um einen Zeiger auf eine Schnittstelle für ein Objekt für die benutzerdefinierten Fehler zurückzugeben.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetCustomErrorObject(ULONG ulRecordNum,
   REFIID riid,IUnknown** ppObject) const throw();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetCustomErrorObject](/previous-versions/windows/desktop/ms725417(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="geterrorinfo"></a> CDBErrorInfo::GetErrorInfo

Aufrufe [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) zurückzugebenden ein [IErrorInfo](/previous-versions/windows/desktop/ms718112(v=vs.85)) Schnittstellenzeiger auf den angegebenen Datensatz.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetErrorInfo(ULONG ulRecordNum,
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetErrorInfo](/previous-versions/windows/desktop/ms711230(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="geterrorparameters"></a> CDBErrorInfo::GetErrorParameters

Aufrufe [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) die Fehlerparameter zurückgegeben.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetErrorParameters(ULONG ulRecordNum,
   DISPPARAMS* pdispparams) const throw();
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IErrorRecords::GetErrorParameters](/previous-versions/windows/desktop/ms715793(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

## <a name="geterrorrecords"></a> CDBErrorInfo::GetErrorRecords

Ruft die Error-Datensätze für das angegebene Objekt ab.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,
   const IID& iid,
   ULONG* pcRecords) throw();

HRESULT GetErrorRecords(ULONG* pcRecords) throw();
```

#### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Eine Schnittstelle für das Objekt für die Error-Datensätze abgerufen.

*iid*<br/>
[in] Die IID der Schnittstelle mit dem Fehler verknüpft ist.

*pcRecords*<br/>
[out] Ein Zeiger auf die (1-basiert) Anzahl von Datensätzen.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Verwenden Sie die erste Form der Funktion, wenn Sie die Schnittstelle zum Abrufen der Fehlerinformationen von überprüfen möchten. Verwenden Sie andernfalls die zweite Form.

## <a name="see-also"></a>Siehe auch

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)