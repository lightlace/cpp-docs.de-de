---
title: CAtlDllModuleT-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13cd0adb860660e06c92e8f02c07721ede391fb7
ms.lasthandoff: 02/24/2017

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
 Abgeleitet von die Klasse `CAtlDllModuleT`.  
  
## <a name="members"></a>Mitglieder  
  
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
|[CAtlDllModuleT::DllMain](#dllmain)|Optionales Einstiegspunkt in einer Dynamic Link Library (DLL).|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Die Registrierung für Objekte in der DLL hinzugefügt Einträge.|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Einträge entfernt in der Registrierung für Objekte in der DLL.|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Gibt eine Klassenfactory zurück. Vom aufgerufenen [DllGetClassObject](#dllgetclassobject).|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlDllModuleT`das Modul für eine Dynamic Link Library (DLL) darstellt, und bietet Funktionen, die alle DLL-Projekte verwendet. Diese Spezialisierung [CAtlModuleT](../../atl/reference/catlmodulet-class.md) Klasse umfasst Unterstützung für die Registrierung.  
  
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
 Wenn das nicht S_OK zurück, wenn die DLL entladen werden kann oder S_FALSE zurückgegeben werden soll.  
  
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
 Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 Optionales Einstiegspunkt in einer Dynamic Link Library (DLL).  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwReason`  
 Wenn Set DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH und DLL_THREAD_DETACH Benachrichtigung Aufrufe deaktiviert sind.  
  
 *lpReserved*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer TRUE zurück.  
  
### <a name="remarks"></a>Hinweise  
 Durch Deaktivieren von DLL_THREAD_ATTACH und DLL_THREAD_DETACH können Benachrichtigungen eine nützliche Optimierung von Multithreadanwendungen sein, die viele DLLs, die häufig erstellen und Löschen von Threads, und diese Benachrichtigungen auf Threadebene Anlage/trennen, dessen DLLs nicht erforderlich.  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 Die Registrierung für Objekte in der DLL hinzugefügt Einträge.  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden. Der Standardwert ist TRUE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 Einträge entfernt in der Registrierung für Objekte in der DLL.  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bUnRegTypeLib`  
 True, wenn die Typbibliothek aus der Registrierung entfernt werden soll. Der Standardwert ist TRUE.  
  
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
 Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) und wird aus Gründen der Abwärtskompatibilität.  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

