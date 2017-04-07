---
title: Klasse CAtlWinModule | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6db3ae9e610605524683e984f2aba602b1daf0d4
ms.lasthandoff: 02/24/2017

---
# <a name="catlwinmodule-class"></a>CAtlWinModule-Klasse
Diese Klasse bietet Unterstützung für ATL-Windowing-Komponenten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Fügt ein Objekt hinzu.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Gibt einen Zeiger auf das Modul Daten.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Unterstützung für alle ATL-Klassen die Windowing-Funktionen erforderlich ist.  
  
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
 Zeiger auf die `_AtlCreateWndData` Struktur initialisiert und das aktuelle Modul hinzugefügt werden soll.  
  
 `pObject`  
 Zeiger auf ein Objekt **dies** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [AtlWinModuleAddCreateWndData](http://msdn.microsoft.com/library/8463a6ed-07ea-4aad-92ec-ded681601b32) welche Initialisiert ein [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) Struktur. Diese Struktur speichert die **dies** Zeiger verwendet, um die Klasseninstanz in Fensterprozeduren zu erhalten.  
  
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
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

