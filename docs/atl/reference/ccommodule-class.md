---
title: CComModule-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d0d5f040d7c6fbe4a4d83da0d589e123588c6bb1
ms.lasthandoff: 03/17/2017

---
# <a name="ccommodule-class"></a>CComModule-Klasse
Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|Erstellt ein Objekt der angegebenen CLSID. Für DLLs.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|Gibt `m_hInst`zurück.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|Gibt `m_hInstResource`zurück.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Gibt `m_hInstTypeLib`zurück.|  
|[CComModule](#init)|Datenmember initialisiert.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|Gibt ein Objekt-Standardklasse Registrierung in der Registrierung.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt. Für EXE-Dateien nur.|  
|[CComModule::RegisterServer](#registerserver)|Aktualisiert die Registrierung für jedes Objekt in der objektzuordnung.|  
|[CComModule::RegisterTypeLib](#registertypelib)|Registriert eine Typbibliothek.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Hebt das Klassenobjekt. Für EXE-Dateien nur.|  
|[CComModule:: Term.](#term)|Frei von Datenelementen.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Entfernt ein Objekt-Standardklasse Registrierung aus der Registrierung.|  
|[CComModule::UnregisterServer](#unregisterserver)|Hebt die Registrierung jedes Objekt in der objektzuordnung.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Register oder hebt die Registrierung eines Objekts-Standardklasse Registrierung.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statisch mit der ATL-Registrierungskomponente verknüpft. Führt das Skript in einer angegebenen Ressource an-oder ein Objekt enthalten sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|Wird synchronisiert den Zugriff auf die Map-Objektinformationen sichergestellt.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Wird synchronisiert den Zugriff auf die Informationen zur Typbibliothek sichergestellt.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Gewährleistet synchronisierten Zugriff auf fensterklasseninformationen und statische Daten, die während der Erstellung verwendet.|  
|[CComModule::m_hInst](#m_hinst)|Enthält das Handle für die Modulinstanz.|  
|[CComModule::m_hInstResource](#m_hinstresource)|Standardmäßig enthält das Handle für die Modulinstanz.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|Standardmäßig enthält das Handle für die Modulinstanz.|  
|[CComModule::m_pObjMap](#m_pobjmap)|Verweist auf die objektzuordnung, die von der Modulinstanz verwaltet.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet, und die ATL-Code-Generierung-Assistenten jetzt verwenden die [CComModule](../../atl/reference/catlautothreadmodule-class.md) und [von CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen. Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Informationen. Die folgenden Informationen ist für die Verwendung mit der Anwendung erstellt, die mit älteren Versionen von ATL `CComModule`ist immer noch Teil der ATL für Abwärtskompatibilität Funktion.  
  
 `CComModule`implementiert ein COM-Server-Modul ermöglicht einen Client den Zugriff auf das Modul Komponenten. `CComModule`unterstützt (in-Process)-DLL und EXE-Datei (local)-Module.  
  
 Ein `CComModule` Instanz eine objektzuordnung verwendet, um einen Satz von Klassendefinitionen Objekt zu verwalten. Die objektzuordnung wird als ein Array von implementiert `_ATL_OBJMAP_ENTRY` Strukturen, und enthält Informationen zu:  
  
-   Eingabe und Beschreibungen der Ergebnisobjekte in der Registrierung entfernen.  
  
-   Instanziieren von Objekten über eine Klassenfactory.  
  
-   Einrichten der Kommunikation zwischen einem Client und dem Stammobjekt in der Komponente.  
  
-   Führt die Verwaltung der Lebensdauer von Klassenobjekten.  
  
 Beim Ausführen des ATL-COM-AppWizard generiert der Assistent automatisch `_Module`, eine globale Instanz von `CComModule` oder eine Klasse abgeleitet. Weitere Informationen über ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
 Zusätzlich zu `CComModule`, ATL stellt [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), der ein Apartment-Modell-Modul für EXE-Dateien und Windows-Dienste implementiert. Leiten Sie das Modul aus `CComAutoThreadModule` Wenn Sie Objekte in mehreren Apartments erstellen möchten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getclassobject"></a>CComModule::GetClassObject  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
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
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppv` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Objekt der angegebenen CLSID und ruft einen Schnittstellenzeiger für dieses Objekt ab.  
  
 `GetClassObject`ist nur auf DLLs verfügbar.  
  
##  <a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HINSTANCE` dieses Modul zu identifizieren.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInst](#m_hinst) -Datenmember.  
  
##  <a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `HINSTANCE`.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInstResource](#m_hinstresource) -Datenmember.  
  
##  <a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `HINSTANCE`.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die [M_hInstTypeLib](#m_hinsttypelib) -Datenmember.  
  
##  <a name="init"></a>CComModule  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträgen.  
  
 `h`  
 [in] Die `HINSTANCE` übergebenen **DLLMain** oder `WinMain`.  
  
 `plibid`  
 [in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert alle Datenmember.  
  
##  <a name="m_csobjmap"></a>CComModule::m_csObjMap  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>Hinweise  
 Wird synchronisiert den Zugriff auf die Objekttabelle sichergestellt.  
  
##  <a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>Hinweise  
 Wird synchronisiert den Zugriff auf die Typbibliothek sichergestellt.  
  
##  <a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>Hinweise  
 Gewährleistet synchronisiert den Zugriff auf fensterklasseninformationen und statische Daten, die während der Erstellung verwendet.  
  
##  <a name="m_hinst"></a>CComModule::m_hInst  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) legt `m_hInst` an das Handle übergeben **DLLMain** oder `WinMain`.  
  
##  <a name="m_hinstresource"></a>CComModule::m_hInstResource  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) legt `m_hInstResource` an das Handle übergeben **DLLMain** oder `WinMain`. Sie können explizit festlegen `m_hInstResource` auf das Handle für eine Ressource.  
  
 Die [GetResourceInstance](#getresourceinstance) Methode gibt das Handle in gespeicherten `m_hInstResource`.  
  
##  <a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig enthält das Handle für die Modulinstanz.  
  
 Die [Init](#init) legt `m_hInstTypeLib` an das Handle übergeben **DLLMain** oder `WinMain`. Sie können explizit festlegen `m_hInstTypeLib` auf das Handle für eine Typbibliothek.  
  
 Die [GetTypeLibInstance](#gettypelibinstance) Methode gibt das Handle in gespeicherten `m_hInstTypeLib`.  
  
##  <a name="m_pobjmap"></a>CComModule::m_pObjMap  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>Hinweise  
 Verweist auf die objektzuordnung, die von der Modulinstanz verwaltet.  
  
##  <a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
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
 [in] Die ProgID des Objekts.  
  
 `lpszVerIndProgID`  
 [in] Die versionsunabhängige ProgID des Objekts.  
  
 `nDescID`  
 [in] Der Bezeichner einer Zeichenfolgenressource für die Beschreibung des Objekts.  
  
 `dwFlags`  
 [in] Gibt das Threadingmodell an, in der Registrierung einzugeben. Mögliche Werte sind **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, oder **AUTPRXFLAG**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt ein Objekt-Standardklasse Registrierung in der Registrierung.  
  
 Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `RegisterClassHelper`.  
  
##  <a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwClsContext`  
 [in] Gibt den Kontext, in dem das Objekt der Klasse ist, ausgeführt werden. Mögliche Werte sind **CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, oder **CLSCTX_LOCAL_SERVER**. Eine Beschreibung dieser Werte finden Sie in [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwFlags`  
 [in] Bestimmt, welche Verbindung auf das Klassenobjekt. Mögliche Werte sind **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, oder **REGCLS_MULTI_SEPARATE**. Eine Beschreibung dieser Werte finden Sie in [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Eine EXE-Klassenobjekt registriert mit OLE, damit andere Anwendung hergestellt werden können. Diese Methode ist nur für EXE-Dateien verfügbar.  
  
##  <a name="registerserver"></a>CComModule::RegisterServer  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bRegTypeLib`  
 [in] Gibt an, ob die Typbibliothek registriert wird. Der Standardwert ist **FALSE**.  
  
 `pCLSID`  
 [in] Verweist auf die CLSID des Objekts, das registriert werden. Wenn **NULL** (Standardwert), werden alle Objekte in der objektzuordnung registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Je nach den `pCLSID` -Parameter, die Registrierung für eine einzelne Klassenobjekt oder für alle Objekte in der objektzuordnung aktualisiert.  
  
 Wenn `bRegTypeLib` ist **TRUE**, die Informationen zur Typbibliothek wird ebenfalls aktualisiert werden.  
  
 Finden Sie unter [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.  
  
 `RegisterServer`wird automatisch aufgerufen, **DLLRegisterServer** für eine DLL oder durch `WinMain` für eine EXE-Datei führen Sie mit der **/RegServer** -Befehlszeilenoption.  
  
##  <a name="registertypelib"></a>CComModule::RegisterTypeLib  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 [in] Zeichenfolge im Format `"\\N"`, wobei `N` ist der ganzzahlige Index, der Ressource, der TYPBIBLIOTHEK.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu einer Typbibliothek und der Registrierung hinzugefügt.  
  
 Enthält die Modulinstanz mehrere Typbibliotheken, verwenden Sie die zweite Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.  
  
##  <a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt das Klassenobjekt. Diese Methode ist nur für EXE-Dateien verfügbar.  
  
##  <a name="term"></a>CComModule:: Term.  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle Datenmember frei.  
  
##  <a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID des Objekts aufgehoben werden.  
  
 `lpszProgID`  
 [in] Die ProgID des Objekts.  
  
 `lpszVerIndProgID`  
 [in] Die versionsunabhängige ProgID des Objekts.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt ein Objekt-Standardklasse Registrierung aus der Registrierung.  
  
 Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `UnregisterClassHelper`.  
  
##  <a name="unregisterserver"></a>CComModule::UnregisterServer  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `bUnRegTypeLib`  
 Wenn **TRUE**, die Typbibliothek wird auch aufgehoben.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, nicht aufgehoben werden. Wenn **NULL** (Standardwert), alle Objekte in der objektzuordnung werden aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Je nach der `pCLSID` Parameter hebt die Registrierung einer einzelnen Klassenobjekt oder alle Objekte in der objektzuordnung.  
  
 `UnregisterServer`wird automatisch aufgerufen, **DLLUnregisterServer** für eine DLL oder durch `WinMain` für eine EXE-Datei führen Sie mit der **/Unregserver** -Befehlszeilenoption.  
  
 Finden Sie unter [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.  
  
##  <a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
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
 Die CLSID des Objekts registriert oder nicht registriert werden.  
  
 `lpszProgID`  
 Die ProgID des Objekts.  
  
 `lpszVerIndProgID`  
 Die versionsunabhängige ProgID des Objekts.  
  
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
 Wenn `bRegister` ist **TRUE**, diese Methode gibt das Objekt-Standardklasse Registrierung in der Registrierung.  
  
 Wenn `bRegister` ist **FALSE**, entfernt die Registrierung des Objekts.  
  
 Abhängig vom Wert der `bRegister`, `UpdateRegistryClass` entweder [RegisterClassHelper](#registerclasshelper) oder [UnregisterClassHelper](#unregisterclasshelper).  
  
 Durch Angabe der [DECLARE_REGISTRY](http://msdn.microsoft.com/library/89b8949b-5c27-4a9c-8a51-ad276bba3a54) -Makro, `UpdateRegistryClass` wird automatisch aufgerufen, wenn die objektzuordnung verarbeitet wird.  
  
##  <a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
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
 [in] Den Namen einer Ressource.  
  
 `nResID`  
 [in] Eine Ressourcen-ID  
  
 `bRegister`  
 [in] Gibt an, ob das Objekt registriert werden soll.  
  
 `pMapEntries`  
 [in] Ein Zeiger auf die Ersatz-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch die `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie weitere Informationen. Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Führt das Skript in die durch angegebene Ressource enthaltenen `lpszRes` oder `nResID`.  
  
 Wenn `bRegister` ist **TRUE**, diese Methode das Objekt in der Registrierung registriert; andernfalls Es hebt die Registrierung des Objekts.  
  
 Durch Angabe der [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) oder [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) -Makro, `UpdateRegistryFromResourceD` wird automatisch aufgerufen, wenn die objektzuordnung verarbeitet wird.  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie die `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, in dem jeder Eintrag einen Variable Platzhalter enthält kombiniert mit einem Wert zur Laufzeit den Platzhalter zu ersetzen. Rufen Sie dann `UpdateRegistryFromResourceD`, übergeben Sie das Array für die `pMapEntries` Parameter. Dadurch werden die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen der Registrierungsstelle Ersatz-Zuordnung.  
  
> [!NOTE]
>  Um einer statischen Verknüpfung mit der ATL-Registrierungskomponente (Registrar) finden Sie unter [UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Weitere Informationen über ersetzbare Parameter und scripting finden Sie im Artikel [die ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
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
 [in] Den Namen einer Ressource.  
  
 `nResID`  
 [in] Eine Ressourcen-ID  
  
 `bRegister`  
 [in] Gibt an, ob das Ressourcenskript registriert werden soll.  
  
 `pMapEntries`  
 [in] Ein Zeiger auf die Ersatz-Zuordnung Speichern von Werten, die das Skript ersetzbare Parameter zugeordnet. ATL verwendet automatisch die `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie weitere Informationen. Verwenden Sie andernfalls die **NULL** default-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Ähnlich wie [UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `UpdateRegistryFromResourceS` erstellt eine statische Verknüpfung zu ATL-Registrierungskomponente (Registrar).  
  
 `UpdateRegistryFromResourceS`wird aufgerufen, automatisch bei der Verarbeitung der objektzuordnung wird vorausgesetzt, Sie fügen `#define _ATL_STATIC_REGISTRY` auf die Datei "stdafx.h".  
  
> [!NOTE]
>  Um Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie die [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) oder [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, in dem jeder Eintrag einen Variable Platzhalter enthält kombiniert mit einem Wert zur Laufzeit den Platzhalter zu ersetzen. Rufen Sie dann `UpdateRegistryFromResourceS`, übergeben Sie das Array für die `pMapEntries` Parameter. Dadurch werden die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen der Registrierungsstelle Ersatz-Zuordnung.  
  
 Weitere Informationen über ersetzbare Parameter und scripting finden Sie im Artikel [die ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

