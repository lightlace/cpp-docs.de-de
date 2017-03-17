---
title: CAtlBaseModule Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4897f6cf7e12a18401720ad663c90491bb0e599d
ms.lasthandoff: 02/24/2017

---
# <a name="catlbasemodule-class"></a>CAtlBaseModule-Klasse
Diese Klasse wird in jedem ATL-Projekt instanziiert.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Fügt eine Ressourceninstanz in die Liste der gespeicherten behandelt.|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Gibt ein Handle auf eine Instanz der angegebenen Ressource zurück.|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Gibt die Modulinstanz aus einem `CAtlBaseModule` Objekt.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Gibt die Ressourceninstanz aus einer `CAtlBaseModule` Objekt.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Entfernt eine Ressourceninstanz aus der Liste der gespeicherten behandelt.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Legt die Resource-Instanz, der ein `CAtlBaseModule` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Eine Variable, die angibt, ob die Modul-Initialisierung fehlgeschlagen ist.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von `CAtlBaseModule` benannte _AtlBaseModule ist in jedem ATL-Projekt, das ein Handle für die Modulinstanz, ein Handle für das Modul mit Ressourcen (die standardmäßig ein und dieselbe sind) und ein Array von Handles für Module, die primäre Ressourcen enthält. `CAtlBaseModule`kann von mehreren Threads sicher zugegriffen werden.  
  
 Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md) Klasse zur Verwendung in früheren Versionen von ATL  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance  
 Fügt eine Ressourceninstanz in die Liste der gespeicherten behandelt.  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hInst`  
 Die Ressourceninstanz hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Ressource wurde erfolgreich hinzugefügt, False andernfalls.  
  
##  <a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule  
 Der Konstruktor.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt das `CAtlBaseModule`-Objekt.  
  
##  <a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt  
 Gibt ein Handle auf eine Instanz der angegebenen Ressource zurück.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *i*  
 Die Anzahl der Ressourceninstanz.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für die Ressourceninstanz oder NULL zurück, wenn keine entsprechenden Instanz der Ressource vorhanden ist.  
  
##  <a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance  
 Gibt die Modulinstanz aus einem `CAtlBaseModule` Objekt.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Modulinstanz zurück.  
  
##  <a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance  
 Gibt die Ressourceninstanz.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Ressourceninstanz.  
  
##  <a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed  
 Eine Variable, die angibt, ob die Modul-Initialisierung fehlgeschlagen ist.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Hinweise  
 True, wenn das Modul initialisiert, False, wenn es konnte nicht initialisiert werden.  
  
##  <a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance  
 Entfernt eine Ressourceninstanz aus der Liste der gespeicherten behandelt.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hInst`  
 Die zu entfernende Ressourceninstanz.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Ressource wurde erfolgreich entfernt, andernfalls false wurde.  
  
##  <a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance  
 Legt die Resource-Instanz, der ein `CAtlBaseModule` Objekt.  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hInst`  
 Die neue Ressourceninstanz.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten Ressource-Instanz zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

