---
title: Registrierung und TypeLib globale Funktionen
ms.date: 03/27/2019
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: c5fdaceb47b6cd09dd9d66f26af1337a8dc6bbae
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58566012"
---
# <a name="registry-and-typelib-global-functions"></a>Registrierung und TypeLib globale Funktionen

Diese Funktionen bieten Unterstützung für das Laden und Registrieren einer Typbibliothek.

> [!IMPORTANT]
>  In den folgenden Tabellen aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|Erstellt den angegebenen Registrierungsschlüssel.|
|[AfxRegDeleteKey](#afxregdeletekey)|Löscht den angegebenen Registrierungsschlüssel.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Ein Hilfsprogramm, um einen Vorschauhandler zu registrieren.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Hilfe beim Aufheben der Registrierung eines vorschauhandlers. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Diese Funktion wird aufgerufen, um die Registrierung einer Typbibliothek aufzuheben|
|[AfxRegOpenKey](#afxregopenkey)|Öffnet den angegebenen Registrierungsschlüssel.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel.|
|[AtlLoadTypeLib](#atlloadtypelib)|Mit dieser Funktion wird eine Typbibliothek geladen.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Mit dieser Funktion können Sie die Registrierung von der angegebenen Ressource aus aktualisieren.|
|[RegistryDataExchange](#registrydataexchange)|Mit dieser Funktion können Sie Lese- und Schreibvorgänge in der Systemregistrierung vornehmen. Wird aufgerufen, indem die [Registrierungsdaten Exchange-Makros](../../atl/reference/registry-data-exchange-macros.md).|

Diese Funktionen steuern, welche Knoten in der Registrierung, die die Anwendung verwendet, um Informationen zu speichern.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Ruft ab, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

Diese Funktion verwenden, um festzustellen, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** (**HKCU**) Knoten.

### <a name="syntax"></a>Syntax

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Parameter

*pEnabled*<br/>
[out] TRUE gibt an, dass die Registrierungsinformationen, um geleitet wird die **HKCU** Knoten FALSE gibt an, dass die Anwendung Informationen in der Registrierung auf den Standardknoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist, andernfalls der HRESULT-Fehler code, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Registrierungsumleitung wird standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird der Zugriff auf die Registrierung zu umgeleitet **HKEY_CURRENT_USER\Software\Classes**.

Die Umleitung ist nicht global. Nur die MFC und ATL-Frameworks sind von diesem registrierungsumleitung betroffen.

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="afxregcreatekey"></a> AfxRegCreateKey

Erstellt den angegebenen Registrierungsschlüssel.

### <a name="syntax"></a>Syntax

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name eines Schlüssels, die diese Funktion wird geöffnet oder erstellt werden soll.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxregdeletekey"></a> AfxRegDeleteKey

Löscht den angegebenen Registrierungsschlüssel.

### <a name="syntax"></a>Syntax

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name des Schlüssels, der gelöscht werden.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxregisterpreviewhandler"></a>

Ein Hilfsprogramm, um einen Vorschauhandler zu registrieren.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Parameter

*lpszCLSID*<br/>
Gibt die CLSID des Handlers.

*lpszShortTypeName*<br/>
Gibt an, die ProgID des Handlers.

*lpszFilterExt*<br/>
Gibt an, die Dateierweiterung mit dieser Handler registriert.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib

Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parameter

*hInstTypeLib*<br/>
Das Handle für die Modulinstanz.

*lpszIndex*<br/>
Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) und [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="afxregopenkey"></a> AfxRegOpenKey

Öffnet den angegebenen Registrierungsschlüssel.

### <a name="syntax"></a>Syntax

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name eines Schlüssels, die diese Funktion wird geöffnet oder erstellt werden soll.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den erstellten Schlüssel erhält.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx

Öffnet den angegebenen Registrierungsschlüssel.

### <a name="syntax"></a>Syntax

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name eines Schlüssels, die diese Funktion wird geöffnet oder erstellt werden soll.

*ulOptions*<br/>
Dieser Parameter ist reserviert und muss NULL sein.

*samDesired*<br/>
Eine Maske, die die gewünschten Zugriffsrechte auf den Schlüssel angibt.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den geöffneten Schlüssel erhält.

*pTM*<br/>
Zeiger auf eine `CAtlTransactionManager` Objekt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

Hilfe beim Aufheben der Registrierung eines vorschauhandlers.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Parameter

*lpszCLSID*<br/>
Gibt die CLSID des Handlers zum aufgehoben werden.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** (**HKCU**) Knoten.

### <a name="syntax"></a>Syntax

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] TRUE gibt an, dass die Registrierungsinformationen, um geleitet wird die **HKCU** Knoten FALSE gibt an, dass die Anwendung Informationen in der Registrierung auf den Standardknoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Rückgabewert

S_OK, wenn die Methode erfolgreich ist, andernfalls der HRESULT-Fehler code, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Registrierungsumleitung wird standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird der Zugriff auf die Registrierung zu umgeleitet **HKEY_CURRENT_USER\Software\Classes**.

Die Umleitung ist nicht global. Nur die MFC und ATL-Frameworks sind von diesem registrierungsumleitung betroffen.

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atlunregistertypelib"></a>  AtlUnRegisterTypeLib

Diese Funktion wird aufgerufen, um die Registrierung einer Typbibliothek aufzuheben.

### <a name="syntax"></a>Syntax

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parameter

*hInstTypeLib*<br/>
Das Handle für die Modulinstanz.

*lpszIndex*<br/>
Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) und [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib

Mit dieser Funktion wird eine Typbibliothek geladen.

### <a name="syntax"></a>Syntax

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>Parameter

*hInstTypeLib*<br/>
Handle für das Modul der Typbibliothek zugeordnet.

*lpszIndex*<br/>
Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.

*pbstrPath*<br/>
Bei erfolgreicher Rückgabe enthält den vollständigen Pfad des Moduls, die der Typbibliothek zugeordnet.

*ppTypeLib*<br/>
Enthält bei erfolgreicher Rückgabe einen Zeiger auf einen Zeiger auf die Bibliothek geladen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [AtlRegisterTypeLib](#atlregistertypelib) und [AtlUnRegisterTypeLib](#atlunregistertypelib).

##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD

Diese Funktion war in Visual Studio 2013 veraltet und wird in Visual Studio 2015 entfernt.

```
<removed>
```

##  <a name="registrydataexchange"></a>  RegistryDataExchange

Mit dieser Funktion können Sie Lese- und Schreibvorgänge in der Systemregistrierung vornehmen.

### <a name="syntax"></a>Syntax

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Parameter

*pT*<br/>
Ein Zeiger auf das aktuelle Objekt.

*rdxOp*<br/>
Ein Enumerationswert, welcher Vorgang angibt, sollte die Funktion durchführen. Finden Sie in der Tabelle im Abschnitt "Hinweise", um die zulässigen Werte.

*pItem*<br/>
Zeiger auf die Daten, die aus gelesen oder in die Registrierung geschrieben werden soll. Die Daten können auch einen Schlüssel aus der Registrierung gelöscht werden darstellen. Der Standardwert ist NULL.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die Makros [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) und [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) erweitern Sie auf eine Funktion aufgerufen, `RegistryDataExchange`.

Die möglichen Enumerationswerte, die angeben, dass der Vorgang die Funktion ausgeführt werden soll, sind in der folgenden Tabelle dargestellt:

|Enum-Wert|Vorgang|
|----------------|---------------|
|eReadFromReg|Lesen von Daten aus der Registrierung.|
|eWriteToReg|Schreiben von Daten in der Registrierung.|
|eDeleteFromReg|Löschen Sie den Schlüssel aus der Registrierung.|

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Funktionen](atl-functions.md)<br/>
[Registrierungsdatenaustausch-Makros](registry-data-exchange-macros.md)
