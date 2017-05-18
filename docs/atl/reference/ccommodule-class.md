---
title: CComModule-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 893efea83bd0d84813a70ec39e5d50fde47dd732
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="ccommodule-class"></a>CComModule-Klasse
Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Erstellt ein Objekt des angegebenen CLSID. Für DLLs.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Gibt `m_hInst`zurück.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Gibt `m_hInstResource`zurück.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Gibt `m_hInstTypeLib`zurück.|  
|[CComModule](#init)|Datenmember initialisiert.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Gibt ein Objekt standardressourcenklasse Registrierung in der systemregistrierung.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt. Für die EXE-Dateien nur.|  
|[CComModule::RegisterServer](#registerserver)|Aktualisiert die systemregistrierung, für jedes Objekt in der objektzuordnung.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Registriert eine Typbibliothek.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Hebt das Klassenobjekt. Für die EXE-Dateien nur.|  
|[CComModule:: Term.](#term)|Gibt die Datenmember frei.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Die standard-Klasse Registrierung eines Objekts entfernt aus der Registrierung.|  
|[CComModule::UnregisterServer](#unregisterserver)|Hebt die Registrierung jedes Objekt in der objektzuordnung auf.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Registriert, oder hebt die Registrierung für ein Objekt standard-Klasse.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statisch mit der ATL-Registrierungskomponente verknüpft. Führt das Skript in einer angegebenen Ressource zu registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Wird synchronisiert den Zugriff auf die Karte Objektinformationen sichergestellt.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Wird sichergestellt, dass synchronisierten Zugriff auf die Informationen in der Typbibliothek.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Wird sichergestellt, dass synchronisierten Zugriff auf die fensterklasseninformationen und statische Daten, die während der fenstererstellung verwendet.|  
|[CComModule::m_hInst](#m_hinst)|Enthält das Handle für die Modulinstanz.|  
|[CComModule::m_hInstResource](#m_hinstresource)|Standardmäßig enthält das Handle für die Modulinstanz.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|Standardmäßig enthält das Handle für die Modulinstanz.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Zeigt auf der objektzuordnung, die von der Modulinstanz verwaltet.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet, und die ATL-Code schemagenerierungs-Assistenten jetzt verwenden die [CComModule](../../atl/reference/catlautothreadmodule-class.md) und [von CAtlModule](../../atl/reference/catlmodule-class.md) abgeleitete Klassen. Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für Weitere Informationen. Die folgenden Informationen ist für die Verwendung mit Anwendungen, die mit älteren Versionen von ATL erstellt `CComModule`ist immer noch Teil der ATL für Abwärtskompatibilität Funktion.  
  
 `CComModule`implementiert eine COM-Server-Modul ermöglicht einen Client den Zugriff auf das Modul Komponenten an. `CComModule`unterstützt (in-Process)-DLL und EXE-Datei (local) Module.  
  
 Ein `CComModule` Instanz eine objektzuordnung verwendet, um einen Satz von Objektdefinitionen Klasse verwalten. Diese objektzuordnung wird als ein Array von implementiert `_ATL_OBJMAP_ENTRY` Strukturen, und enthält Informationen zu:  
  
-   Eingeben und Beschreibungen der Ergebnisobjekte in der Registrierung entfernen.  
  
-   Instanziieren von Objekten über einer Klassenfactory.  
  
-   Beim Herstellen der Kommunikation zwischen einem Client und das Stammobjekt in der Komponente.  
  
-   Verwaltung der Lebensdauer von Klassenobjekten wird durchgeführt.  
  
 Wenn Sie die ATL-COM-AppWizard ausführen, generiert der Assistent automatisch `_Module`, eine globale Instanz von `CComModule` oder eine Klasse abgeleitet. Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
 Zusätzlich zu `CComModule`, ATL stellt [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), die einem Apartmentmodell Modul für die EXE-Dateien und Windows-Dienste implementiert. Leiten Sie das Modul aus `CComAutoThreadModule` beim Erstellen von Objekten in mehreren Apartments werden sollen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getclassobject"></a>CComModule::GetClassObject  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rclsid`  
 [in] Die CLSID des Objekts erstellt werden.  
  
 `riid`  
 [in] Die IID der angeforderten Schnittstelle.  
  
 `ppv`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppv` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Objekt der angegebenen CLSID und ruft einen Schnittstellenzeiger für dieses Objekt ab.  
  
 `GetClassObject`ist nur auf DLLs verfügbar.  
  
##  <a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HINSTANCE` dieses Modul identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInst](#m_hinst) -Datenmember.  
  
##  <a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `HINSTANCE`.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInstResource](#m_hinstresource) -Datenmember.  
  
##  <a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `HINSTANCE`.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInstTypeLib](#m_hinsttypelib) -Datenmember.  
  
##  <a name="init"></a>CComModule  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträge.  
  
 `h`  
 [in] Die `HINSTANCE` übergeben **DLLMain** oder `WinMain`.  
  
 `plibid`  
 [in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Alle Datenmember initialisiert.  
  
##  <a name="m_csobjmap"></a>CComModule::m_csObjMap  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Hinweise  
 Wird sichergestellt, dass synchronisierten Zugriff auf der objektzuordnung.  
  
##  <a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird sichergestellt, dass synchronisierten Zugriff auf die Typbibliothek.  
  
##  <a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Hinweise  
 Wird sichergestellt, dass synchronisierten Zugriff auf fensterklasseninformationen und statische Daten, die während der fenstererstellung verwendet.  
  
##  <a name="m_hinst"></a>CComModule::m_hInst  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) -Methode legt `m_hInst` an das Handle übergeben **DLLMain** oder `WinMain`.  
  
##  <a name="m_hinstresource"></a>CComModule::m_hInstResource  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) -Methode legt `m_hInstResource` an das Handle übergeben **DLLMain** oder `WinMain`. Sie können explizit festlegen `m_hInstResource` an das Handle auf eine Ressource.  
  
 Die [GetResourceInstance](#getresourceinstance) Methodenrückgabe das Handle in gespeicherten `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) -Methode legt `m_hInstTypeLib` an das Handle übergeben **DLLMain** oder `WinMain`. Sie können explizit festlegen `m_hInstTypeLib` an das Handle in eine Typbibliothek.  
  
 Die [GetTypeLibInstance](#gettypelibinstance) Methodenrückgabe das Handle in gespeicherten `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>CComModule::m_pObjMap  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Hinweise  
 Zeigt auf der objektzuordnung, die von der Modulinstanz verwaltet.  
  
##  <a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID des Objekts registriert werden.  
  
 `lpszProgID`  
 [in] Die ProgID dem Objekt zugeordnet ist.  
  
 `lpszVerIndProgID`  
 [in] Die versionsunabhängige ProgID dem Objekt zugeordnet.  
  
 `nDescID`  
 [in] Der Bezeichner des eine Zeichenfolgenressource für die Beschreibung des Objekts.  
  
 `dwFlags`  
 [in] Gibt das Threadingmodell an, in der Registrierung einzugeben. Mögliche Werte sind **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, oder **AUTPRXFLAG**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt ein Objekt standardressourcenklasse Registrierung in der systemregistrierung.  
  
 Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwClsContext`  
 [in] Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind **CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, oder **CLSCTX_LOCAL_SERVER**. Eine Beschreibung dieser Werte finden Sie in [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwFlags`  
 [in] Bestimmt die Verbindungstypen auf das Klassenobjekt. Mögliche Werte sind **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, oder **REGCLS_MULTI_SEPARATE**. Eine Beschreibung dieser Werte finden Sie in [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Eine EXE-Klassenobjekt registriert mit OLE, damit andere Anwendungen hergestellt werden können. Diese Methode ist nur für EXE-Dateien verfügbar.  
  
##  <a name="registerserver"></a>CComModule::RegisterServer  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 [in] Gibt an, ob die Typbibliothek registriert wird. Der Standardwert ist **"false"**.  
  
 `pCLSID`  
 [in] Verweist auf die CLSID des Objekts, das registriert werden. Wenn **NULL** (Standardwert), werden alle Objekte in der objektzuordnung registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Je nach den `pCLSID` Parameter, aktualisiert die Registrierung für eine einzelne Klassenobjekt oder für alle Objekte in der objektzuordnung.  
  
 Wenn `bRegTypeLib` ist **"true"**, die Informationen in der Typbibliothek werden auch aktualisiert werden.  
  
 Finden Sie unter [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.  
  
 `RegisterServer`aufgerufen wird, automatisch vom **DLLRegisterServer** für eine DLL oder durch `WinMain` für eine EXE-Datei an, führen Sie mit der **/RegServer** -Befehlszeilenoption.  
  
##  <a name="registertypelib"></a>CComModule::RegisterTypeLib  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 [in] Zeichenfolge im Format `"\\N"`, wobei `N` ist der ganzzahlige Index, der die TYPBIBLIOTHEK-Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Fügt Informationen zu einer Typbibliothek in der systemregistrierung.  
  
 Wenn die Modulinstanz mehrere Typbibliotheken enthält, verwenden Sie die zweite Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.  
  
##  <a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt das Klassenobjekt. Diese Methode ist nur für EXE-Dateien verfügbar.  
  
##  <a name="term"></a>CComModule:: Term.  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei.  
  
##  <a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID des Objekts, nicht aufgehoben werden.  
  
 `lpszProgID`  
 [in] Die ProgID dem Objekt zugeordnet ist.  
  
 `lpszVerIndProgID`  
 [in] Die versionsunabhängige ProgID dem Objekt zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die standard-Klasse Registrierung eines Objekts entfernt aus der Registrierung.  
  
 Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>CComModule::UnregisterServer  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `bUnRegTypeLib`  
 Wenn **"true"**, die Typbibliothek wird auch die Registrierung aufgehoben.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn **NULL** (Standardwert), alle Objekte in der objektzuordnung werden aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Je nach den `pCLSID` Parameter, hebt die Registrierung eines Klassenobjekts für einzelne oder alle Objekte in der objektzuordnung auf.  
  
 `UnregisterServer`aufgerufen wird, automatisch vom **DLLUnregisterServer** für eine DLL oder durch `WinMain` für eine EXE-Datei an, führen Sie mit der **/Unregserver** -Befehlszeilenoption.  
  
 Finden Sie unter [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.  
  
##  <a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die CLSID des Objekts, der registriert oder deren Registrierung aufgehoben wird.  
  
 `lpszProgID`  
 Die ProgID dem Objekt zugeordnet ist.  
  
 `lpszVerIndProgID`  
 Die versionsunabhängige ProgID dem Objekt zugeordnet.  
  
 `nDescID`  
 Der Bezeichner der Zeichenfolgenressource für die Beschreibung des Objekts.  
  
 `szDesc`  
 Eine Zeichenfolge mit der Beschreibung des Objekts.  
  
 `dwFlags`  
 Gibt das Threadingmodell an, in der Registrierung einzugeben. Mögliche Werte sind **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, oder **AUTPRXFLAG**.  
  
 `bRegister`  
 Gibt an, ob das Objekt registriert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bRegister` ist **"true"**, diese Methode gibt standardressourcenklasse-Registrierung für das Objekt in der systemregistrierung.  
  
 Wenn `bRegister` ist **"false"**, Registrierung für das Objekt entfernt.  
  
 Abhängig vom Wert der `bRegister`, `UpdateRegistryClass` aufruft, entweder [RegisterClassHelper](#registerclasshelper) oder [UnregisterClassHelper](#unregisterclasshelper).  
  
 Durch Angabe der [DECLARE_REGISTRY](registry-macros.md#declare_registry) Makro `UpdateRegistryClass` wird automatisch aufgerufen, wenn Ihre objektzuordnung verarbeitet wird.  
  
##  <a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
virtual HRESULT UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszRes`  
 [in] Der Name einer Ressource.  
  
 `nResID`  
 [in] Ein Ressourcen-ID.  
  
 `bRegister`  
 [in] Gibt an, ob das Objekt registriert werden soll.  
  
 `pMapEntries`  
 [in] Ein Zeiger auf die Austausch-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch die `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter den Hinweisen für Details. Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Führt das Skript in die durch die angegebene Ressource enthaltenen `lpszRes` oder `nResID`.  
  
 Wenn `bRegister` ist **"true"**, diese Methode registriert das Objekt in der systemregistrierung; anderenfalls er hebt die Registrierung des Objekts.  
  
 Durch Angabe der [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) Makro `UpdateRegistryFromResourceD` wird automatisch aufgerufen, wenn Ihre objektzuordnung verarbeitet wird.  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit zu ersetzen, geben Sie keine der `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, wobei jeder Eintrag einen Variablen Platzhalter enthält gekoppelt mit einem Wert zur Laufzeit den Platzhalter ersetzen. Rufen Sie anschließend `UpdateRegistryFromResourceD`, übergeben Sie das Array für die `pMapEntries` Parameter. Dadurch wird die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen, die die Registrierungsstelle Ersatz-Zuordnung.  
  
> [!NOTE]
>  Um mit der ATL-Registrierungskomponente (Registrar) statisch zu verknüpfen, finden Sie unter [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Weitere Informationen zu ersetzbare Parameter und scripting finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
virtual HRESULT UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszRes`  
 [in] Der Name einer Ressource.  
  
 `nResID`  
 [in] Ein Ressourcen-ID.  
  
 `bRegister`  
 [in] Gibt an, ob das Ressourcenskript registriert werden soll.  
  
 `pMapEntries`  
 [in] Ein Zeiger auf die Austausch-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch die `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter den Hinweisen für Details. Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `UpdateRegistryFromResourceS` erstellt eine statische Verknüpfung zu ATL-Registrierungskomponente (Registrar).  
  
 `UpdateRegistryFromResourceS`wird aufgerufen, die automatisch bei der Verarbeitung der objektzuordnung, sofern Sie hinzufügen `#define _ATL_STATIC_REGISTRY` auf Ihre "stdafx.h".  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit zu ersetzen, geben Sie keine der [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, wobei jeder Eintrag einen Variablen Platzhalter enthält gekoppelt mit einem Wert zur Laufzeit den Platzhalter ersetzen. Rufen Sie anschließend `UpdateRegistryFromResourceS`, übergeben Sie das Array für die `pMapEntries` Parameter. Dadurch wird die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen, die die Registrierungsstelle Ersatz-Zuordnung.  
  
 Weitere Informationen zu ersetzbare Parameter und scripting finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

