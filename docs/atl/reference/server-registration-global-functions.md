---
title: Globale Funktionen für Server-Registrierung
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: f97a4ff0dc28077d42fe0f8ca4992946db4082f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441789"
---
# <a name="server-registration-global-functions"></a>Globale Funktionen für Server-Registrierung

Diese Funktionen bieten Unterstützung für das Registrieren und Aufheben der Registrierung für Server-Objekte in der objektzuordnung.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Diese Funktion wird aufgerufen, um Objekte der Klasse aus einem COM­Modul zu widerrufen.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Diese Funktion wird aufgerufen, um das Klassenobjekt abrufen.|

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer

Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parameter

*pComModule*<br/>
Zeiger auf die COM-Modul.

*bRegTypeLib*<br/>
True, wenn die Typbibliothek registriert werden.

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das registriert werden. Wenn der Wert NULL ist, werden alle Objekte in der objektzuordnung registriert werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`AtlComModuleRegisterServer` führt der objektzuordnung für ATL-automatisch generiert und registriert jedes Objekt in der Zuordnung. Wenn *pCLSID* ist nicht NULL, dann nur das Objekt, das als *pCLSID* registriert ist; andernfalls werden alle Objekte registriert.

Diese Funktion wird aufgerufen, indem [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).

##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer

Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parameter

*pComModule*<br/>
Zeiger auf die COM-Modul.

*bUnRegTypeLib*<br/>
True, wenn die Typbibliothek registriert werden.

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn der Wert NULL werden alle Objekte in der objektzuordnung aufgehoben werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`AtlComModuleUnregisterServer` führt die Zuordnung der ATL-Objekt, und hebt die Registrierung für jedes Objekt in der Zuordnung. Wenn *pCLSID* ist nicht NULL, dann nur das Objekt, das als *pCLSID* wird aufgehoben wurde, andernfalls aller Objekte aufgehoben werden.

Diese Funktion wird aufgerufen, indem [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).

##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects

Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parameter

*pComModule*<br/>
Zeiger auf die COM-Modul.

*dwClsContext*<br/>
Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER. Finden Sie unter [CLSCTX](/windows/desktop/api/wtypesbase/ne-wtypesbase-tagclsctx) Weitere Details.

*dwFlags*<br/>
Bestimmt die Art der Verbindung mit dem Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE. Finden Sie unter [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (veraltet in ATL 7.0) und [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).

##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects

Diese Funktion wird aufgerufen, um eine oder mehrere Klassenfactorys aus der ROT (Running Object Table) zu entfernen.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Parameter

*pComModule*<br/>
Zeiger auf die COM-Modul.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (veraltet in ATL 7.0) und [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).

##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject

Diese Funktion wird aufgerufen, um die Klassenfactory zurückzugeben.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>Parameter

*pComModule*<br/>
Zeiger auf die COM-Modul.

*rclsid*<br/>
Die CLSID des Objekts erstellt werden.

*riid*<br/>
Die IID der angeforderten Schnittstelle.

*ppv*<br/>
Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *Ppv* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion wird verwendet, indem [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (veraltet in ATL 7.0) und [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
