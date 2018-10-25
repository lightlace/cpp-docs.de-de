---
title: CAtlComModule-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0600476df22c3d87bc5694e9ffe2af09f4542439
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063262"
---
# <a name="catlcommodule-class"></a>CAtlComModule-Klasse

Diese Klasse implementiert, ein COM-Server-Modul.

## <a name="syntax"></a>Syntax

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlComModule::CAtlComModule](#catlcommodule)|Der Konstruktor.|
|[CAtlComModule:: ~ CAtlComModule](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|Rufen Sie diese Methode, um die Registrierung des Systems für jedes Objekt in der objektzuordnung zu aktualisieren.|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Rufen Sie diese Methode, um eine Typbibliothek zu registrieren.|
|[CAtlComModule::UnregisterServer](#unregisterserver)|Rufen Sie diese Methode zum Aufheben der Registrierung jedes Objekt in der objektzuordnung.|
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Rufen Sie diese Methode, um die Registrierung einer Typbibliothek aufzuheben.|

## <a name="remarks"></a>Hinweise

`CAtlComModule` implementiert ein COM-Server-Modul, einen Client den Zugriff auf die Modul Komponenten zulassen.

Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md) Klasse, die in früheren Versionen von ATL verwendet werden. Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="catlcommodule"></a>  CAtlComModule::CAtlComModule

Der Konstruktor.

```
CAtlComModule() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert das Modul.

##  <a name="dtor"></a>  CAtlComModule:: ~ CAtlComModule

Der Destruktor.

```
~CAtlComModule();
```

### <a name="remarks"></a>Hinweise

Gibt alle Klassenfactorys frei.

##  <a name="registerserver"></a>  CAtlComModule::RegisterServer

Rufen Sie diese Methode, um die Registrierung des Systems für jedes Objekt in der objektzuordnung zu aktualisieren.

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parameter

*bRegTypeLib*<br/>
True, wenn die Typbibliothek registriert werden. Der Standardwert ist "false".

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das registriert werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung registriert wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft die globale Funktion [AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver).

##  <a name="registertypelib"></a>  CAtlComModule::RegisterTypeLib

Rufen Sie diese Methode, um eine Typbibliothek zu registrieren.

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>Parameter

*lpszIndex*<br/>
Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index der TYPELIB-Ressourcen ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Fügt Informationen über eine Typbibliothek in die systemregistrierung. Wenn die Modulinstanz mehrere Bibliotheken enthält, verwenden Sie die erste Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.

##  <a name="unregisterserver"></a>  CAtlComModule::UnregisterServer

Rufen Sie diese Methode zum Aufheben der Registrierung jedes Objekt in der objektzuordnung.

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>Parameter

*bRegTypeLib*<br/>
"True", wenn die Typbibliothek nicht registriert werden soll. Der Standardwert ist "false".

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung aufgehoben.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft die globale Funktion [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

##  <a name="unregistertypelib"></a>  CAtlComModule::UnRegisterTypeLib

Rufen Sie diese Methode, um die Registrierung einer Typbibliothek aufzuheben.

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>Parameter

*lpszIndex*<br/>
Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index der TYPELIB-Ressourcen ist.

### <a name="remarks"></a>Hinweise

Entfernt Informationen über eine Typbibliothek aus der Registrierung des Systems. Wenn die Modulinstanz mehrere Bibliotheken enthält, verwenden Sie die erste Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

## <a name="see-also"></a>Siehe auch

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
