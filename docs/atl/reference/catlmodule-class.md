---
title: Klasse von CAtlModule | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlModule
- CAtlModule
- ATL.CAtlModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>Von CAtlModule-Klasse
Diese Klasse enthält Methoden, die von mehreren ATL-Modulklassen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|Der Konstruktor.|  
|[Von CAtlModule:: ~ von CAtlModule](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Überschreiben Sie diese Methode zum Hinzufügen von Parametern zur ATL-Registrierungskomponente (Registrar) Ersatz-Zuordnung.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Fügt eine neue Funktion aufgerufen werden, wenn das Modul beendet wird.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Gibt den globalen Schnittstellenzeiger zurück.|  
|[CAtlModule::GetLockCount](#getlockcount)|Gibt die Anzahl der Sperren zurück.|  
|[CAtlModule::Lock](#lock)|Erhöht die Anzahl der Sperren.|  
|[CAtlModule::Term](#term)|Gibt alle Datenmember frei.|  
|[CAtlModule::Unlock](#unlock)|Verringert die Sperrenanzahl.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Diese Methode wird aufgerufen, indem Sie `UpdateRegistryFromResourceD` zum Durchführen der registrierungsaktualisierung.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Enthält die GUID für das aktuelle Modul.|  
|[CAtlModule::m_pGIT](#m_pgit)|Ein Zeiger auf die Global Interface Table.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CAtlDllModuleT-Klasse](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md), und [CAtlServiceModuleT Klasse](../../atl/reference/catlservicemodulet-class.md) Applications DLL, EXE-Anwendungen und Windows-Dienste, bzw. unterstützen.  
  
 Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).  
  
 Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameaddcommonrgsreplacementsa--catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 Überschreiben Sie diese Methode zum Hinzufügen von Parametern zur ATL-Registrierungskomponente (Registrar) Ersatz-Zuordnung.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pRegistrar*  
 Reserviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzbare Parameter ermöglichen einer Registrierungsstelle Client zur Laufzeit Daten anzugeben. Zu diesem Zweck verwaltet die Registrierungsstelle eine Ersatz-Zuordnung in der er ersetzbare Parameter in Ihrem Skript zugeordneten Werte eingibt. Die Registrierungsstelle nimmt diese Einträge zur Laufzeit.  
  
 Finden Sie unter [mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) für weitere Details.  
  
##  <a name="a-nameaddtermfunca--catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModule::AddTermFunc  
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
  
##  <a name="a-namecatlmodulea--catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtlModule::CAtlModule  
 Der Konstruktor.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Datenmember initialisiert, und einen kritischen Abschnitt, um das Modul Thread initiiert.  
  
##  <a name="a-namedtora--catlmodulecatlmodule"></a><a name="dtor"></a>Von CAtlModule:: ~ von CAtlModule  
 Der Destruktor.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei.  
  
##  <a name="a-namegetgitptra--catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Ruft einen Zeiger der globalen Schnittstellentabelle ab.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ppGIT`  
 Ein Zeiger auf eine Variable, die um den Zeiger der globalen Schnittstellentabelle erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen Fehlercode zurück. E_POINTER wird zurückgegeben, wenn `ppGIT` gleich NULL ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Global Interface Table-Objekt ist nicht vorhanden, es erstellt wird und seine Adresse wird in der Membervariablen gespeichert [CAtlModule::m_pGIT](#m_pgit).  
  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn `ppGIT` gleich NULL ist, oder wenn der Global Interface Table-Zeiger kann nicht abgerufen werden.  
  
 Finden Sie unter [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) Informationen auf der globalen Schnittstellentabelle.  
  
##  <a name="a-namegetlockcounta--catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule::GetLockCount  
 Gibt die Anzahl der Sperren zurück.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sperren zurück. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="a-namelocka--catlmodulelock"></a><a name="lock"></a>CAtlModule::Lock  
 Erhöht die Anzahl der Sperren.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Erhöht die Anzahl der Sperren, und gibt den aktualisierten Wert. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="a-namemlibida--catlmodulemlibid"></a><a name="m_libid"></a>CAtlModule::m_libid  
 Enthält die GUID für das aktuelle Modul.  
  
```
static GUID m_libid;
```  
  
##  <a name="a-namempgita--catlmodulempgit"></a><a name="m_pgit"></a>CAtlModule::m_pGIT  
 Ein Zeiger auf die Global Interface Table.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="a-nameterma--catlmoduleterm"></a><a name="term"></a>CAtlModule::Term  
 Gibt alle Datenmember frei.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei. Diese Methode wird vom Destruktor aufgerufen.  
  
##  <a name="a-nameunlocka--catlmoduleunlock"></a><a name="unlock"></a>CAtlModule::Unlock  
 Verringert die Sperrenanzahl.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Verringert die Sperrenanzahl und gibt den aktualisierten Wert. Dieser Wert möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="a-nameupdateregistryfromresourceda--catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind.  
  
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
 Den Namen einer Ressource.  
  
 `nResID`  
 Eine Ressourcen-ID  
  
 `bRegister`  
 **True,** , wenn das Objekt erfasst werden sollen; **FALSE** andernfalls.  
  
 `pMapEntries`  
 Ein Zeiger auf die Ersatz-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Führt das Skript in die durch angegebene Ressource enthaltenen *LpszRes oder nResID*. Wenn `bRegister` ist **TRUE**, diese Methode das Objekt in der Registrierung registriert; andernfalls entfernt das Objekt aus der Registrierung.  
  
 Um einer statischen Verknüpfung mit der ATL-Registrierungskomponente (Registrar) finden Sie unter [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Diese Methode ruft [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) und [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="a-nameupdateregistryfromresourcedhelpera--catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 Diese Methode wird aufgerufen, indem Sie `UpdateRegistryFromResourceD` zum Durchführen der registrierungsaktualisierung.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszRes`  
 Den Namen einer Ressource.  
  
 `bRegister`  
 Gibt an, ob das Objekt registriert werden soll.  
  
 `pMapEntries`  
 Ein Zeiger auf die Ersatz-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stellt die Implementierung der [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="a-nameupdateregistryfromresourcesa--catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind. Diese Methode an, die statisch mit der ATL-Registrierungskomponente verknüpft.  
  
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
 Eine Ressourcen-ID  
  
 `lpszRes`  
 Den Namen einer Ressource.  
  
 `bRegister`  
 Gibt an, ob das Ressourcenskript registriert werden soll.  
  
 `pMapEntries`  
 Ein Zeiger auf die Ersatz-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch %-Modul. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `CAtlModule::UpdateRegistryFromResourceS` erstellt eine statische Verknüpfung zu ATL-Registrierungskomponente (Registrar).  
  
## <a name="see-also"></a>Siehe auch  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)  

