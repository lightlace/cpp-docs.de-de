---
title: CAtlBaseModule-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: d382d1fe7d50a2fdeefc9b477625580792de7d6f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284761"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule-Klasse

Diese Klasse ist in jedem ATL-Projekt instanziiert.

## <a name="syntax"></a>Syntax

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Fügt eine Ressourceninstanz in die Liste der gespeicherten Handles an.|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Gibt ein Handle zu einer Instanz der angegebenen Ressource zurück.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Gibt die Modulinstanz aus einer `CAtlBaseModule` Objekt.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Gibt die Ressourceninstanz aus einer `CAtlBaseModule` Objekt.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Entfernt eine Ressourceninstanz in der Liste der gespeicherten Handles an.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Legt die Ressourceninstanz, der eine `CAtlBaseModule` Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Eine Variable, die angibt, wenn die Initialisierung des Moduls ein Fehler auftritt.|

## <a name="remarks"></a>Hinweise

Eine Instanz von `CAtlBaseModule` benannte _AtlBaseModule in jedem ATL-Projekt, mit der ein Handle für die Modulinstanz, die ein Handle für das Modul mit Ressourcen (die Standardeinstellung identisch sind) und ein Array von Handles für Module, die primären vorhanden ist Ressourcen zu. `CAtlBaseModule` kann von mehreren Threads sicher zugegriffen werden.

Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md) Klasse, die in früheren Versionen von ATL verwendet werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance

Fügt eine Ressourceninstanz in die Liste der gespeicherten Handles an.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parameter

*hInst*<br/>
Die Ressourceninstanz, die hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Ressource wurde erfolgreich hinzugefügt, wird "false" andernfalls.

##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule

Der Konstruktor.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Hinweise

Erstellt das `CAtlBaseModule`-Objekt.

##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt

Gibt ein Handle zu einer Instanz der angegebenen Ressource zurück.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Parameter

*i*<br/>
Die Anzahl der Ressourceninstanz.

### <a name="return-value"></a>Rückgabewert

Gibt das Handle auf die Ressourceninstanz oder NULL zurück, wenn keine entsprechende Ressourceninstanz vorhanden ist.

##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance

Gibt die Modulinstanz aus einer `CAtlBaseModule` Objekt.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Modulinstanz zurück.

##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance

Gibt die Ressourceninstanz zurück.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Ressourceninstanz zurück.

##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed

Eine Variable, die angibt, wenn die Initialisierung des Moduls ein Fehler auftritt.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>Hinweise

True, wenn das Modul initialisiert, "false", wenn es konnte nicht initialisiert werden.

##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance

Entfernt eine Ressourceninstanz in der Liste der gespeicherten Handles an.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parameter

*hInst*<br/>
Die zu entfernende Ressourceninstanz.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Ressource wurde erfolgreich entfernt, andernfalls false wurde.

##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance

Legt die Ressourceninstanz, der eine `CAtlBaseModule` Objekt.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parameter

*hInst*<br/>
Die neue Ressourceninstanz.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte Ressource-Instanz zurück.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
