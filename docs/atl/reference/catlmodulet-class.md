---
title: CAtlModuleT Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29088c56d7020b38febb96be7512771a258e25fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361687"
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
 Die Klasse abgeleitet `CAtlModuleT`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|Initialisiert den Datenmember, enthält die GUID des aktuellen Moduls.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|Die EXE-Datei hinzugefügt zur Registrierung.|  
|[CAtlModuleT::RegisterServer](#registerserver)|Den Dienst hinzugefügt zur Registrierung.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Entfernt die EXE-Datei aus der Registrierung.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Aktualisiert die EXE-Informationen in der Registrierung.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlModuleT`, abgeleitet [von CAtlModule](../../atl/reference/catlmodule-class.md), eine ausführbare Datei (EXE) oder ein Dienst (EXE) ATL-Modul implementiert. Ein ausführbares Modul ist eine lokale, Out-of-Process-Server, während eine Dienstmodul einer Windows-Anwendung ist, die im Hintergrund ausgeführt, beim Starten von Windows wird.  
  
 `CAtlModuleT` bietet Unterstützung für die Initialisierung, registrieren und Aufheben der Registrierung des Moduls.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT  
 Der Konstruktor.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CAtlModuleT::InitLibId](#initlibid).  
  
##  <a name="initlibid"></a>  CAtlModuleT::InitLibId  
 Initialisiert den Datenmember, enthält die GUID des aktuellen Moduls.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird aufgerufen, die vom Konstruktor [CAtlModuleT::CAtlModuleT](#catlmodulet).  
  
##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId  
 Die EXE-Datei hinzugefügt zur Registrierung.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer  
 Den Dienst hinzugefügt zur Registrierung.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden. Der Standardwert ist "false".  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das registriert werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung registriert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId  
 Entfernt die EXE-Datei aus der Registrierung.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer  
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
 Verweist auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId  
 Aktualisiert die EXE-Informationen in der Registrierung.  
  
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
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
