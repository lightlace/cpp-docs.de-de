---
title: CAtlDllModuleT-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs: C++
helpviewer_keywords: CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 650924898532e352df30d7e8173620b974f30138
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT-Klasse
Diese Klasse stellt das Modul für eine DLL.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CAtlDllModuleT`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Der Konstruktor.|  
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Testet, ob die DLL entladen werden kann.|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Gibt eine Klassenfactory zurück.|  
|[CAtlDllModuleT::DllMain](#dllmain)|Der optionale Einstiegspunkt in einer Dynamic Link Library (DLL).|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Einträge hinzugefügt in der systemregistrierung für Objekte in der DLL.|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Entfernt Einträge in der systemregistrierung für Objekte in der DLL an.|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Gibt eine Klassenfactory zurück. Vom aufgerufenen [DllGetClassObject](#dllgetclassobject).|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlDllModuleT`das Modul für eine Dynamic Link Library (DLL) darstellt, und bietet Funktionen, die alle DLL-Projekte verwendet. Diese Art der Spezialisierung von [CAtlModuleT](../../atl/reference/catlmodulet-class.md) Klasse bietet Unterstützung für die Registrierung.  
  
 Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT  
 Der Konstruktor.  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT  
 Der Destruktor.  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow  
 Testet, ob die DLL entladen werden kann.  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die DLL entladen werden kann oder ein "S_FALSE" zurückgegeben, wenn dies nicht möglich.  
  
##  <a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject  
 Gibt die Klassenfactory zurück.  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rclsid`  
 Die CLSID des Objekts erstellt werden.  
  
 `riid`  
 Die IID der angeforderten Schnittstelle.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 Der optionale Einstiegspunkt in einer Dynamic Link Library (DLL).  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwReason`  
 Wenn Set DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH und DLL_THREAD_DETACH Benachrichtigung Aufrufe deaktiviert sind.  
  
 *lpReserved*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Deaktivieren die DLL_THREAD_ATTACH und DLL_THREAD_DETACH mitgeteilt, dass Aufrufe eine nützliche Optimierung für Multithreadanwendungen sein können, die viele DLLs haben, die häufig erstellen und Löschen von Threads und deren DLLs benötigen keine Benachrichtigungen zu dieser Thread auf Dokumentebene Anfügen/Trennen.  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 Einträge hinzugefügt in der systemregistrierung für Objekte in der DLL.  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden. Der Standardwert ist "true".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 Entfernt Einträge in der systemregistrierung für Objekte in der DLL an.  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bUnRegTypeLib`  
 True, wenn die Typbibliothek aus der Registrierung entfernt werden soll. Der Standardwert ist "true".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="getclassobject"></a>CAtlDllModuleT::GetClassObject  
 Erstellt ein Objekt der angegebenen CLSID.  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rclsid`  
 Die CLSID des Objekts erstellt werden.  
  
 `riid`  
 Die IID der angeforderten Schnittstelle.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) und wird aus Gründen der Abwärtskompatibilität.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
