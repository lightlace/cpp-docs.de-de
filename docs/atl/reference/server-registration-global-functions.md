---
title: Server-Registrierung globale Funktionen | Microsoft-Dokumentation
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
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4ace3bb50d824827071260e3f43cec3cda32742f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="server-registration-global-functions"></a>Server-Registrierung globale Funktionen
Diese Funktionen bieten Unterstützung für das Registrieren und Aufheben der Registrierung von Server-Objekte in der objektzuordnung.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Diese Funktion wird aufgerufen, um Objekte der Klasse aus einem COM­Modul zu widerrufen.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Diese Funktion wird aufgerufen, um das Klassenobjekt abzurufen.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
 Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf die COM-Modul.  
  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das registriert werden. Bei NULL werden alle Objekte in der objektzuordnung registriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `AtlComModuleRegisterServer`führt die Objekttabelle von ATL automatisch generiert und registriert jedes Objekt in der Zuordnung. Wenn `pCLSID` ist nicht NULL, dann nur das Objekt gemäß `pCLSID` registriert ist; andernfalls werden alle Objekte registriert.  
  
 Diese Funktion wird aufgerufen, indem [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
 Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf die COM-Modul.  
  
 `bUnRegTypeLib`  
 True, wenn die Typbibliothek registriert werden.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, nicht aufgehoben werden. Bei NULL werden alle Objekte in der objektzuordnung aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `AtlComModuleUnregisterServer`führt die Zuordnung der ATL-Objekt, und hebt die Registrierung jedes Objekt in der Zuordnung. Wenn `pCLSID` ist nicht NULL, dann nur das Objekt gemäß `pCLSID` aufgehoben wird, andernfalls aller Objekte aufgehoben werden.  
  
 Diese Funktion wird aufgerufen, indem [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
 Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf die COM-Modul.  
  
 `dwClsContext`  
 Gibt den Kontext, in dem das Objekt der Klasse ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER. Finden Sie unter [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) für weitere Details.  
  
 `dwFlags`  
 Bestimmt, welche Verbindung auf das Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE. Finden Sie unter [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) für weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (veraltete in ATL 7.0) und [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 Diese Funktion wird aufgerufen, um eine oder mehrere Klassenfactorys aus der ROT (Running Object Table) zu entfernen.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf die COM-Modul.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (veraltete in ATL 7.0) und [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
 Diese Funktion wird aufgerufen, um die Klassenfactory zurückzugeben.  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf die COM-Modul.  
  
 `rclsid`  
 Die CLSID des Objekts erstellt werden.  
  
 `riid`  
 Die IID der angeforderten Schnittstelle.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion ist der von verwendete [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (veraltete in ATL 7.0) und [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

