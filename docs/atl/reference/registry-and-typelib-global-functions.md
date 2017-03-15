---
title: Registrierung und TypeLib globale Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9d454f2eac1b29785fe40a480fc43c7c34a861a3
ms.lasthandoff: 02/24/2017

---
# <a name="registry-and-typelib-global-functions"></a>Registrierung und TypeLib globale Funktionen
Diese Funktionen bieten Unterstützung für das Laden und Registrieren einer Typbibliothek.  
  
> [!IMPORTANT]
>  In den folgenden Tabellen aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](#atlregistertypelib)|Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Diese Funktion wird aufgerufen, um die Registrierung einer Typbibliothek aufzuheben|  
|[AtlLoadTypeLib](#atlloadtypelib)|Mit dieser Funktion wird eine Typbibliothek geladen.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Mit dieser Funktion können Sie die Registrierung von der angegebenen Ressource aus aktualisieren.|  
|[RegistryDataExchange](#registrydataexchange)|Mit dieser Funktion können Sie Lese- und Schreibvorgänge in der Systemregistrierung vornehmen. Aufgerufen von der [Registrierungsdaten Exchange Makros](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Diese Funktionen steuern, welche Knoten in der Registrierung der Anwendung verwendet, um Informationen zu speichern.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Ruft ab, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

## <a name="a-nameatlgetperuserregistrationa-atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
Mit dieser Funktion können Sie bestimmen, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** (**HKCU**) Knoten.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `pEnabled`  
 `TRUE`Gibt an, dass die Registrierungsinformationen geleitet wird die **HKCU** Knoten; `FALSE` gibt an, dass die Anwendung Informationen in der Registrierung auf dem Knoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist, andernfalls ist der `HRESULT` Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Registrierungsumleitung ist standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird der Zugriff auf die Registrierung an umgeleitet **HKEY_CURRENT_USER\Software\Classes**.  
  
 Die Umleitung ist nicht global. Diese registrierungsumleitung sind nur die MFC- und ATL-Frameworks betroffen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="a-nameatlregistertypeliba--atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 Diese Funktion wird aufgerufen, um eine Typbibliothek zu registrieren.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstTypeLib`  
 Das Handle für die Modulinstanz.  
  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der Typ Bibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) und [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

## <a name="a-nameatlsetperuserregistrationa-atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** (**HKCU**) Knoten.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Gibt an, dass die Registrierungsinformationen geleitet wird die **HKCU** Knoten; `FALSE` gibt an, dass die Anwendung Informationen in der Registrierung auf dem Knoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich ist, andernfalls ist der `HRESULT` Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Registrierungsumleitung ist standardmäßig nicht aktiviert. Wenn Sie diese Option aktivieren, wird der Zugriff auf die Registrierung an umgeleitet **HKEY_CURRENT_USER\Software\Classes**.  
  
 Die Umleitung ist nicht global. Diese registrierungsumleitung sind nur die MFC- und ATL-Frameworks betroffen.  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

##  <a name="a-nameatlunregistertypeliba--atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
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
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der Typ Bibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) und [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h

##  <a name="a-nameatlloadtypeliba--atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib  
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
 Handle für das Modul, die der Typbibliothek zugeordnet.  
  
 `lpszIndex`  
 Zeichenfolge im Format "\\\N", wobei N der ganzzahlige Index, der Typ Bibliotheksressource ist. NULL kann sein, wenn kein Index erforderlich ist.  
  
 *pbstrPath*  
 Enthält bei erfolgreicher Rückgabe den vollständigen Pfad des Moduls der Typbibliothek zugeordnet.  
  
 `ppTypeLib`  
 Enthält bei erfolgreicher Rückgabe einen Zeiger auf einen Zeiger auf die Typbibliothek geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [AtlRegisterTypeLib](#atlregistertypelib) und [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="a-nameatlupdateregistryfromresourceda--atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 Diese Funktion war in Visual Studio 2013 veraltet und wird in Visual Studio 2015 entfernt.  
  
```
<removed>
```  
  
### <a name="parameters"></a>Parameter  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameregistrydataexchangea--registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange  
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
 Ein Enumerationswert, der den Vorgang angibt, sollten die Funktion ausführen. Siehe die Tabelle im Abschnitt "Hinweise" für die zulässigen Werte.  
  
 `pItem`  
 Ein Zeiger auf die Daten, die aus lesen oder in die Registrierung geschrieben werden soll. Die Daten können auch einen Schlüssel aus der Registrierung gelöscht werden darstellen. Der Standardwert ist NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Makros [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) und [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) eine Funktion aufgerufen, erweitern Sie `RegistryDataExchange`.  
  
 Die möglichen Enumerationswerte, die darauf hinweisen, dass der Vorgang der Funktion durchgeführt werden soll, werden in der folgenden Tabelle dargestellt:  
  
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






