---
title: CAtlWinModule Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14b918747d9b7bee1b661eebd61fbb35325861e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358051"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule-Klasse
Diese Klasse bietet Unterstützung für ATL Windowing-Komponenten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Der Konstruktor.|  
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Fügt ein Datenobjekt hinzu.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Gibt einen Zeiger auf das Fenster Module-Datenobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Unterstützung für alle ATL-Klassen die Fensterfunktionen erfordern.  
  
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
 `pData`  
 Zeiger auf die `_AtlCreateWndData` Struktur initialisiert und das aktuelle Modul hinzugefügt werden.  
  
 `pObject`  
 Zeiger auf ein Objekt **dies** Zeiger.  
  
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
 Diese Methode gibt einen Zeiger auf eine `_AtlCreateWndData` Struktur.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die `_AtlCreateWndData` Struktur, die zuvor hinzugefügten mit [CAtlWinModule::AddCreateWndData](#addcreatewnddata), oder NULL, wenn kein Objekt verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
