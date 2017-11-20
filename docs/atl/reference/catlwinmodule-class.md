---
title: CAtlWinModule Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs: C++
helpviewer_keywords: CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 59f555f129548b3ced008b61364fa4a9900e062d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="catlwinmodule-class"></a>CAtlWinModule-Klasse
Diese Klasse bietet Unterstützung für ATL Windowing-Komponenten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData  
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
  
##  <a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule  
 Der Konstruktor.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Initialisierung fehlschlägt, eine **EXCEPTION_NONCONTINUABLE** Ausnahme ausgelöst.  
  
##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule  
 Der Destruktor.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData  
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
