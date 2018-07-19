---
title: CAtlModule-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 5291ae4783e252341371844ca08e390958c3ff89
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882571"
---
# <a name="catlmodule-class"></a>CAtlModule-Klasse
Diese Klasse stellt die Methoden, die durch verschiedene ATL-Modulklassen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Der Konstruktor.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Überschreiben Sie diese Methode zum Hinzufügen von Parametern zur Zuordnung ATL-Registrierungskomponente (Registrar) ersetzt.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Fügt eine neue Funktion aufgerufen werden, wenn das Modul beendet wird.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Gibt den globalen Schnittstellenzeiger zurück.|  
|[CAtlModule::GetLockCount](#getlockcount)|Gibt die Anzahl der Sperren zurück.|  
|[CAtlModule::Lock](#lock)|Wird der sperrzähler erhöht.|  
|[CAtlModule::Term](#term)|Gibt alle Datenmember frei.|  
|[CAtlModule::Unlock](#unlock)|Verringert die Sperrenanzahl.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Diese Methode wird aufgerufen, indem `UpdateRegistryFromResourceD` um das Registrierungsupdate durchzuführen.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Enthält die GUID des aktuellen Moduls.|  
|[CAtlModule::m_pGIT](#m_pgit)|Zeiger auf die globale Schnittstellentabelle.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md), und [CAtlServiceModuleT-Klasse](../../atl/reference/catlservicemodulet-class.md) um DLL-Anwendungen, EXE-Anwendungen zu unterstützen und Windows, beziehungsweise Datendienste.  
  
 Weitere Informationen zu Modulen in ATL, finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
 Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements  
 Überschreiben Sie diese Methode zum Hinzufügen von Parametern zur Zuordnung ATL-Registrierungskomponente (Registrar) ersetzt.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pRegistrar*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzbare Parameter ermöglichen eine Registrierungsstelle Client Laufzeitdaten angeben. Zu diesem Zweck verwaltet die Registrierungsstelle eine Ersatz-Zuordnung, die in das die ersetzbaren Parametern in Ihrem Skript zugeordneten Werte wechselt Sie in. Die Registrierungsstelle wird diese Einträge zur Laufzeit.  
  
 Finden Sie im Thema [mithilfe von ersetzbaren Parametern (der Registrierungspräprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) Weitere Details.  
  
##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc  
 Fügt eine neue Funktion aufgerufen werden, wenn das Modul beendet wird.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pFunc*  
 Zeiger auf die Funktion hinzufügen.  
  
 *Data Warehouse*  
 Benutzerdefinierte Daten an die Funktion übergeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="catlmodule"></a>  CAtlModule::CAtlModule  
 Der Konstruktor.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Datenmember initialisiert, und einen kritischen Abschnitt, um die Modul Thread initiiert.  
  
##  <a name="dtor"></a>  CAtlModule:: ~ CAtlModule  
 Der Destruktor.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei.  
  
##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr  
 Ruft einen Zeiger auf die globale Schnittstellentabelle ab.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *ppGIT*  
 Zeiger auf eine Variable, die um den Zeiger auf die globale Schnittstellentabelle erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder ein Fehlercode bei einem Fehler zurück. E_POINTER wird zurückgegeben, wenn *PpGIT* gleich NULL ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das globale Schnittstellentabelle-Objekt ist nicht vorhanden, Sie erstellt wird und seine Adresse sich in der Membervariablen befindet [CAtlModule::m_pGIT](#m_pgit).  
  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn *PpGIT* ist gleich NULL ist, oder wenn der globale Schnittstellentabelle Zeiger kann nicht abgerufen werden.  
  
 Finden Sie unter [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) Informationen auf der globalen Schnittstellentabelle.  
  
##  <a name="getlockcount"></a>  CAtlModule::GetLockCount  
 Gibt die Anzahl der Sperren zurück.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sperren zurück. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="lock"></a>  CAtlModule::Lock  
 Wird der sperrzähler erhöht.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wird der sperrzähler erhöht, und gibt den aktualisierten Wert zurück. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="m_libid"></a>  CAtlModule::m_libid  
 Enthält die GUID des aktuellen Moduls.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>  CAtlModule::m_pGIT  
 Zeiger auf die globale Schnittstellentabelle.  
  
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
 Verringert die Sperrenanzahl und den aktualisierten Wert zurückgibt. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="updateregistryfromresourced"></a>  CAtlModule::UpdateRegistryFromResourceD  
 Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.  
  
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
 *lpszRes*  
 Ein Ressourcenname.  
  
 *nResID*  
 Eine Ressourcen-ID  
  
 *bRegistrieren Sie sich*  
 True, wenn das Objekt registriert werden soll. "False" andernfalls.  
  
 *pMapEntries*  
 Ein Zeiger auf die Ersatz-Zuordnung ersetzbare Parameter des Skripts zugeordneten Werte zu speichern. ATL wird automatisch %-Modul verwendet. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls den Standardwert NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Führt das Skript in die Ressource anhand des enthaltenen *LpszRes oder nResID*. Wenn *bRegistrieren Sie sich* "true", wird diese Methode registriert das Objekt in der systemregistrierung; andernfalls das Objekt aus der Registrierung entfernt.  
  
 Um statisch mit der ATL-Registrierungskomponente (Registrar) zu verknüpfen, finden Sie unter [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Diese Methode ruft [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) und [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper  
 Diese Methode wird aufgerufen, indem `UpdateRegistryFromResourceD` um das Registrierungsupdate durchzuführen.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszRes*  
 Ein Ressourcenname.  
  
 *bRegistrieren Sie sich*  
 Gibt an, ob das Objekt registriert werden soll.  
  
 *pMapEntries*  
 Ein Zeiger auf die Ersatz-Zuordnung ersetzbare Parameter des Skripts zugeordneten Werte zu speichern. ATL wird automatisch %-Modul verwendet. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls den Standardwert NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stellt die Implementierung des [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>  CAtlModule::UpdateRegistryFromResourceS  
 Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.  
  
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
 *nResID*  
 Eine Ressourcen-ID  
  
 *lpszRes*  
 Ein Ressourcenname.  
  
 *bRegistrieren Sie sich*  
 Gibt an, ob das Ressourcenskript registriert werden soll.  
  
 *pMapEntries*  
 Ein Zeiger auf die Ersatz-Zuordnung ersetzbare Parameter des Skripts zugeordneten Werte zu speichern. ATL wird automatisch %-Modul verwendet. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls den Standardwert NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `CAtlModule::UpdateRegistryFromResourceS` erstellt einen statischen Link zu der ATL-Registrierungskomponente (Registrar).  
  
## <a name="see-also"></a>Siehe auch  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)  
