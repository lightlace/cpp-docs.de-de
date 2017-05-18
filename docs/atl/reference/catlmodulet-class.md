---
title: Klasse CAtlModuleT | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
dev_langs:
- C++
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9c0c6a2302932df06db7166d83fe9a561dfe38ac
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodulet-class"></a>CAtlModuleT-Klasse
Diese Klasse implementiert eine ATL-Modul.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `CAtlModuleT`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|Initialisiert den Datenmember, enthält die GUID für das aktuelle Modul.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|Die Registrierung hinzugefügt der EXE-Datei.|  
|[CAtlModuleT::RegisterServer](#registerserver)|Die Registrierung hinzugefügt des Diensts.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Entfernt die EXE-Datei aus der Registrierung.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Die EXE-Informationen in der Registrierung aktualisiert.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlModuleT`, von abgeleiteten [von CAtlModule](../../atl/reference/catlmodule-class.md), eine ausführbare Datei (EXE) oder einer ausführbaren Datei (EXE) ATL-Modul implementiert. Ein ausführbares Modul ist eine lokale, Out-of-Process-Server ist ein dienstermittlungsmodul eine Windows-Anwendung, die im Hintergrund ausgeführt wird, wenn Windows gestartet wird.  
  
 `CAtlModuleT`bietet Unterstützung für die Initialisierung, Registrierung und Aufheben der Registrierung des Moduls.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT  
 Der Konstruktor.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlModuleT::InitLibId](#initlibid).  
  
##  <a name="initlibid"></a>CAtlModuleT::InitLibId  
 Initialisiert den Datenmember, enthält die GUID für das aktuelle Modul.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Vom Konstruktor aufgerufen, [CAtlModuleT::CAtlModuleT](#catlmodulet).  
  
##  <a name="registerappid"></a>CAtlModuleT::RegisterAppId  
 Die Registrierung hinzugefügt der EXE-Datei.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="registerserver"></a>CAtlModuleT::RegisterServer  
 Die Registrierung hinzugefügt des Diensts.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden. Der Standardwert ist FALSE.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das registriert werden. Wenn NULL (der Standardwert), alle Objekte in der objektzuordnung registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId  
 Entfernt die EXE-Datei aus der Registrierung.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="unregisterserver"></a>CAtlModuleT::UnregisterServer  
 Entfernt den Dienst aus der Registrierung.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bUnRegTypeLib`  
 True, wenn auch die Typbibliothek nicht aufgehoben werden.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, nicht aufgehoben werden. Wenn NULL (der Standardwert), alle Objekte in der objektzuordnung aufgehoben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId  
 Die EXE-Informationen in der Registrierung aktualisiert.  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegister`  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Von CAtlModule-Klasse](../../atl/reference/catlmodule-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

