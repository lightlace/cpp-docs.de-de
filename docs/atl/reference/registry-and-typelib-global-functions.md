---
title: Registrierung und TypeLib globale Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
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
ms.openlocfilehash: 9f05db468d5d7fffce149d7a92ba29615c3ae7c1
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="registry-and-typelib-global-functions"></a>Registrierung und TypeLib globale Funktionen
Diese Funktionen bieten Unterstützung für das Laden und Registrieren einer Typbibliothek.  
  
> [!IMPORTANT]
>  In den folgenden Tabellen aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die im Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AfxRegCreateKey](#afxrefcreatekey)|Den angegebene Registrierungsschlüssel wird erstellt.|
|[AfxRegDeleteKey](#afxrefdeletekey)|Löscht den angegebenen Registrierungsschlüssel.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Ein Hilfsprogramm, um einen Vorschauhandler zu registrieren.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Ein Hilfsprogramm, einen Vorschauhandler aufgehoben werden soll. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Diese Funktion wird aufgerufen, um die Registrierung einer Typbibliothek aufzuheben|  
|[AfxRegOpenKey](#afxregopenkey)|Öffnet den angegebenen Registrierungsschlüssel.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel.|
|[AtlLoadTypeLib](#atlloadtypelib)|Mit dieser Funktion wird eine Typbibliothek geladen.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Mit dieser Funktion können Sie die Registrierung von der angegebenen Ressource aus aktualisieren.|  
|[RegistryDataExchange](#registrydataexchange)|Mit dieser Funktion können Sie Lese- und Schreibvorgänge in der Systemregistrierung vornehmen. Wird aufgerufen, indem Sie die [Registrierungsdaten Exchange Makros](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Diese Funktionen steuern, welche Knoten in der Registrierung des Programms verwendet wird, um Informationen zu speichern.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Ruft ab, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Legt fest, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

## <a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
Mit dieser Funktion können Sie bestimmen, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** (**HKCU**) Knoten.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `pEnabled`  
 `TRUE`Gibt an, dass die Registrierungsinformationen weitergeleitet wird die **HKCU** Knoten `FALSE` gibt an, dass die Anwendung auf den Standardknoten für die Informationen in der Registrierung schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist, andernfalls ist der `HRESULT` Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Registrierungsumleitung wird standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird Zugriff auf die Registrierung zu umgeleitet **HKEY_CURRENT_USER\Software\Classes**.  
  
 Die Umleitung ist nicht global. Nur die MFC und ATL-Frameworks sind von diesem registrierungsumleitung betroffen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

 ## <a name="afxregcreatekey"></a>AfxRegCreateKey
 Den angegebene Registrierungsschlüssel wird erstellt.  
  
### <a name="syntax"></a>Syntax  
  
```  
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name eines Schlüssels, der diese Funktion wird geöffnet oder erstellt werden soll.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt, werden soll.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  

### <a name="requirements"></a>Anforderungen  
 **Header:** „afxpriv.h“  

## <a name="afxregdeletekey"></a>AfxRegDeleteKey
Löscht den angegebenen Registrierungsschlüssel.  
  
### <a name="syntax"></a>Syntax  
  
```  
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name des Schlüssels, der gelöscht werden.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** „afxpriv.h“  

## <a name="afxregisterpreviewhandler"></a>
Ein Hilfsprogramm, um einen Vorschauhandler zu registrieren.  
  
### <a name="syntax"></a>Syntax  
  
```  
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszCLSID`  
 Gibt die CLSID des ereignishandlers.  
  
 `lpszShortTypeName`  
 Gibt an, die ProgID des Handler.  
  
 `lpszFilterExt`  
 Gibt an, die Dateierweiterung dieser Handler registriert.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h   

##  <a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstTypeLib`  
 Das Handle für die Modulinstanz.  
  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) und [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

 ## <a name="afxregopenkey"></a>AfxRegOpenKey
 Öffnet den angegebenen Registrierungsschlüssel.  
  
### <a name="syntax"></a>Syntax  
  
```  
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name eines Schlüssels, der diese Funktion wird geöffnet oder erstellt werden soll.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den erstellten Schlüssel erhält.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** „afxpriv.h“  

## <a name="afxregopenkeyex"></a>AfxRegOpenKeyEx
Öffnet den angegebenen Registrierungsschlüssel. 

### <a name="syntax"></a>Syntax  
  
```  
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Ein Handle für ein Öffnen des Registrierungsschlüssels.  
  
 `lpSubKey`  
 Der Name eines Schlüssels, der diese Funktion wird geöffnet oder erstellt werden soll.  
  
 `ulOptions`  
 Dieser Parameter ist reserviert und muss 0 (null) sein.  
  
 `samDesired`  
 Eine Maske, die die gewünschten Zugriffsrechte auf den Schlüssel angibt.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für die geöffnete Schlüssel erhält.  
  
 `pTM`  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** „afxpriv.h“  

 ## <a name="afxunregisterpreviewhandler"></a>AfxUnregisterPreviewHandler
 Ein Hilfsprogramm, einen Vorschauhandler aufgehoben werden soll.  
  
### <a name="syntax"></a>Syntax  
  
```  
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszCLSID`  
 Gibt die CLSID des Handlers zum aufgehoben werden.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

## <a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
Legt fest, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** (**HKCU**) Knoten.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Gibt an, dass die Registrierungsinformationen weitergeleitet wird die **HKCU** Knoten `FALSE` gibt an, dass die Anwendung auf den Standardknoten für die Informationen in der Registrierung schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist, andernfalls ist der `HRESULT` Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Registrierungsumleitung wird standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird Zugriff auf die Registrierung zu umgeleitet **HKEY_CURRENT_USER\Software\Classes**.  
  
 Die Umleitung ist nicht global. Nur die MFC und ATL-Frameworks sind von diesem registrierungsumleitung betroffen.  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
 Diese Funktion wird aufgerufen, um die Registrierung einer Typbibliothek aufzuheben.  
  
### <a name="syntax"></a>Syntax  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstTypeLib`  
 Das Handle für die Modulinstanz.  
  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) und [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

##  <a name="atlloadtypelib"></a>AtlLoadTypeLib  
 Mit dieser Funktion wird eine Typbibliothek geladen.  
  
### <a name="syntax"></a>Syntax  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstTypeLib`  
 Handle für das Modul die Typbibliothek zugeordnet.  
  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der typbibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
 *pbstrPath*  
 Nach erfolgreicher Rückkehr enthält den vollständigen Pfad des Moduls der Typbibliothek zugeordnet.  
  
 `ppTypeLib`  
 Nach erfolgreicher Rückkehr die enthält eines Zeigers auf einen Zeiger auf die geladenen Typbibliothek aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [AtlRegisterTypeLib](#atlregistertypelib) und [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 Diese Funktion war in Visual Studio 2013 veraltet und wird in Visual Studio 2015 entfernt.  
  
```
<removed>
```  
  

  
##  <a name="registrydataexchange"></a>RegistryDataExchange  
 Mit dieser Funktion können Sie Lese- und Schreibvorgänge in der Systemregistrierung vornehmen.  

### <a name="syntax"></a>Syntax  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 Ein Zeiger auf das aktuelle Objekt.  
  
 *rdxOp*  
 Ein Enumerationswert, welcher Vorgang angibt, sollte die Funktion ausführen. Siehe die Tabelle im Abschnitt "Hinweise", um die zulässigen Werte.  
  
 `pItem`  
 Zeiger auf die Daten, die Lese- und in die Registrierung geschrieben werden. Die Daten können auch einen Schlüssel aus der Registrierung gelöscht werden sollen darstellen. Der Standardwert ist NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Makros [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) und [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) erweitern Sie auf eine Funktion, die Aufrufe `RegistryDataExchange`.  
  
 Die möglichen Enumerationswerte, die darauf hinweisen, dass der Vorgang der Funktion ausgeführt werden soll, werden in der folgenden Tabelle dargestellt:  
  
|Enum-Wert|Vorgang|  
|----------------|---------------|  
|eReadFromReg|Lesen von Daten aus der Registrierung.|  
|eWriteToReg|Schreiben von Daten in der Registrierung.|  
|eDeleteFromReg|Löschen Sie den Schlüssel aus der Registrierung.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

## <a name="see-also"></a>Siehe auch  
 [Funktionen](atl-functions.md)
 [Registrierungsdaten Exchange-Makros](registry-data-exchange-macros.md)






