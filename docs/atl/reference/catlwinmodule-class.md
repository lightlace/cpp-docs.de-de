---
title: CAtlWinModule-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269460"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule-Klasse

Diese Klasse bietet Unterstützung für ATL-Windowing-Komponenten.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Der Konstruktor.|
|[CAtlWinModule::~CAtlWinModule](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Fügt ein Datenobjekt hinzu.|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Gibt einen Zeiger auf das Datenobjekt für Fenster-Modul.|

## <a name="remarks"></a>Hinweise

Diese Klasse bietet Unterstützung für alle ATL-Klassen die Windowing-Funktionen erforderlich ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="addcreatewnddata"></a>  CAtlWinModule::AddCreateWndData

Diese Methode initialisiert und fügt eine `_AtlCreateWndData` Struktur.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Parameter

*pData*<br/>
Zeiger auf die `_AtlCreateWndData` Struktur initialisiert und auf das aktuelle Modul hinzugefügt werden.

*pObject*<br/>
Zeiger auf ein Objekt des **dies** Zeiger.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) welche Initialisiert ein [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur. Diese Struktur speichert die **dies** -Zeiger ist, verwendet, um die Klasseninstanz in Fensterprozeduren abzurufen.

##  <a name="catlwinmodule"></a>  CAtlWinModule::CAtlWinModule

Der Konstruktor.

```
CAtlWinModule();
```

### <a name="remarks"></a>Hinweise

Wenn die Initialisierung fehlschlägt, eine **EXCEPTION_NONCONTINUABLE** Ausnahme ausgelöst.

##  <a name="dtor"></a>  CAtlWinModule:: ~ CAtlWinModule

Der Destruktor.

```
~CAtlWinModule();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="extractcreatewnddata"></a>  CAtlWinModule::ExtractCreateWndData

Diese Methode gibt einen Zeiger auf ein `_AtlCreateWndData` Struktur.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `_AtlCreateWndData` Struktur, die zuvor hinzugefügte mit [CAtlWinModule::AddCreateWndData](#addcreatewnddata), oder NULL, wenn kein Objekt verfügbar ist.

## <a name="see-also"></a>Siehe auch

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
