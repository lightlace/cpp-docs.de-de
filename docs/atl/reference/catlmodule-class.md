---
title: Klasse von CAtlModule | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be5d5a777d4b9aed9ee4d07016771ee91c913b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365281"
---
# <a name="catlmodule-class"></a>Von CAtlModule-Klasse
Diese Klasse enthält Methoden, die von mehreren ATL-Modulklassen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Der Konstruktor.|  
|[Von CAtlModule:: ~ von CAtlModule](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Überschreiben Sie diese Methode, um die Parameter der ATL-Registrierungskomponente (Registrar) Ersatz-Zuordnung hinzufügen.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Fügt eine neue Funktion aufgerufen werden, wenn das Modul beendet wird.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Gibt den globalen Schnittstellenzeiger zurück.|  
|[CAtlModule::GetLockCount](#getlockcount)|Gibt die Anzahl der Sperren zurück.|  
|[CAtlModule::Lock](#lock)|Inkrementiert den Verweiszähler der Sperre.|  
|[CAtlModule::Term](#term)|Gibt alle Datenmember frei.|  
|[CAtlModule::Unlock](#unlock)|Verringert die Sperrenanzahl.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Diese Methode wird aufgerufen, indem `UpdateRegistryFromResourceD` das Update der Registrierung ausführen.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Enthält die GUID des aktuellen Moduls.|  
|[CAtlModule::m_pGIT](#m_pgit)|Ein Zeiger auf die globale Schnittstellentabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md), und [CAtlServiceModuleT Klasse](../../atl/reference/catlservicemodulet-class.md) um DLL-Anwendungen, EXE-Anwendungen zu unterstützen und Windows-Dienste, bzw.  
  
 Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
 Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements  
 Überschreiben Sie diese Methode, um die Parameter der ATL-Registrierungskomponente (Registrar) Ersatz-Zuordnung hinzufügen.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pRegistrar*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzbare Parameter ermöglichen einer Registrierungsstelle Client zur Laufzeit Daten anzugeben. Zu diesem Zweck verwaltet die Registrierungsstelle eine Ersatz-Zuordnung in die er die Werte der ersetzbare Parameter in Ihrem Skript zugeordnet wird. Die Registrierungsstelle stellt diese Einträge zur Laufzeit.  
  
 Finden Sie im Thema [mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) Weitere Details.  
  
##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc  
 Fügt eine neue Funktion aufgerufen werden, wenn das Modul beendet wird.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pFunc*  
 Zeiger auf die Funktion hinzufügen.  
  
 `dw`  
 Benutzerdefinierte Daten, die an die Funktion übergeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="catlmodule"></a>  CAtlModule::CAtlModule  
 Der Konstruktor.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Datenmember initialisiert, und einen kritischen Abschnitt, um das Modul Thread initiiert.  
  
##  <a name="dtor"></a>  Von CAtlModule:: ~ von CAtlModule  
 Der Destruktor.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei.  
  
##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr  
 Ruft einen Zeiger auf der globalen Schnittstellentabelle ab.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ppGIT`  
 Ein Zeiger auf eine Variable, die um den Zeiger zu der globalen Schnittstellentabelle erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder ein Fehlercode bei einem Fehler zurück. E_POINTER wird zurückgegeben, wenn `ppGIT` gleich NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der globalen Schnittstellentabelle-Objekt ist nicht vorhanden, er erstellt wird, und seine Adresse sich in die Membervariable befindet [CAtlModule::m_pGIT](#m_pgit).  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `ppGIT` gleich NULL, oder wenn der Zeiger der globalen Schnittstellentabelle abgerufen werden kann.  
  
 Finden Sie unter [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) Informationen auf der globalen Schnittstellentabelle.  
  
##  <a name="getlockcount"></a>  CAtlModule::GetLockCount  
 Gibt die Anzahl der Sperren zurück.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sperren zurück. Dieser Wert möglicherweise nützlich für die Diagnose und Debuggen.  
  
##  <a name="lock"></a>  CAtlModule::Lock  
 Inkrementiert den Verweiszähler der Sperre.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Inkrementiert die Sperrenanzahl und gibt den aktualisierten Wert zurück. Dieser Wert möglicherweise nützlich für die Diagnose und Debuggen.  
  
##  <a name="m_libid"></a>  CAtlModule::m_libid  
 Enthält die GUID des aktuellen Moduls.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>  CAtlModule::m_pGIT  
 Ein Zeiger auf die globale Schnittstellentabelle.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>  CAtlModule::Term  
 Gibt alle Datenmember frei.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei. Diese Methode wird vom Destruktor aufgerufen.  
  
##  <a name="unlock"></a>  CAtlModule::Unlock  
 Verringert die Sperrenanzahl.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Verringert die Sperrenanzahl und den aktualisierten Wert zurückgibt. Dieser Wert möglicherweise nützlich für die Diagnose und Debuggen.  
  
##  <a name="updateregistryfromresourced"></a>  CAtlModule::UpdateRegistryFromResourceD  
 Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszRes`  
 Der Name einer Ressource.  
  
 `nResID`  
 Ein Ressourcen-ID.  
  
 `bRegister`  
 **"True"** , wenn das Objekt registriert werden soll; **"False"** andernfalls.  
  
 `pMapEntries`  
 Ein Zeiger auf die Austausch-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Führt das Skript in die durch die angegebene Ressource enthaltenen *LpszRes oder nResID*. Wenn `bRegister` ist **"true"**, diese Methode registriert das Objekt in der systemregistrierung; andernfalls entfernt das Objekt aus der Registrierung.  
  
 Um mit der ATL-Registrierungskomponente (Registrar) statisch zu verknüpfen, finden Sie unter [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Diese Methode ruft [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) und [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper  
 Diese Methode wird aufgerufen, indem `UpdateRegistryFromResourceD` das Update der Registrierung ausführen.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszRes`  
 Der Name einer Ressource.  
  
 `bRegister`  
 Gibt an, ob das Objekt registriert werden soll.  
  
 `pMapEntries`  
 Ein Zeiger auf die Austausch-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stellt die Implementierung des [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>  CAtlModule::UpdateRegistryFromResourceS  
 Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nResID`  
 Ein Ressourcen-ID.  
  
 `lpszRes`  
 Der Name einer Ressource.  
  
 `bRegister`  
 Gibt an, ob das Ressourcenskript registriert werden soll.  
  
 `pMapEntries`  
 Ein Zeiger auf die Austausch-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `CAtlModule::UpdateRegistryFromResourceS` erstellt eine statische Verknüpfung zu ATL-Registrierungskomponente (Registrar).  
  
## <a name="see-also"></a>Siehe auch  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)  
