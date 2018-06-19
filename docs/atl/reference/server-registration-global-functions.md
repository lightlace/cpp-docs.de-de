---
title: Globale Funktionen für Server-Registrierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a4141ab5ff27e44f663a4d5f267c2b7d754283
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364704"
---
# <a name="server-registration-global-functions"></a>Server-Registrierung globale Funktionen
Diese Funktionen bieten Unterstützung für das Registrieren und Aufheben der Registrierung Serverobjekte in der objektzuordnung.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Diese Funktion wird aufgerufen, um Objekte der Klasse von einem COM­Modul zu widerrufen.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Diese Funktion wird aufgerufen, um das Klassenobjekt zu erhalten.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer  
 Diese Funktion wird aufgerufen, um alle Objekte in der Objektzuordnung zu registrieren.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf das COM-Modul.  
  
 `bRegTypeLib`  
 True, wenn die Typbibliothek registriert werden.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das registriert werden. Wenn der Wert NULL ist, werden alle Objekte in der objektzuordnung registriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `AtlComModuleRegisterServer` führt der objektzuordnung für ATL automatisch generiert und registriert jedes Objekt in der Zuordnung. Wenn `pCLSID` ist nicht NULL, dann nur das Objekt verweist auf `pCLSID` registriert ist; andernfalls werden alle Objekte registriert.  
  
 Diese Funktion wird aufgerufen, indem [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver).  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 Diese Funktion wird aufgerufen, um die Registrierung aller Objekte in der Objektzuordnung aufzuheben.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf das COM-Modul.  
  
 `bUnRegTypeLib`  
 True, wenn die Typbibliothek registriert werden.  
  
 `pCLSID`  
 Verweist auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn der Wert NULL werden alle Objekte in der objektzuordnung aufgehoben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 `AtlComModuleUnregisterServer` führt die Zuordnung der ATL-Objekt, und hebt die Registrierung jedes Objekt in der Zuordnung. Wenn `pCLSID` ist nicht NULL, dann nur das Objekt verweist auf `pCLSID` aufgehoben ist andernfalls alle Objekte, deren Registrierung aufgehoben werden.  
  
 Diese Funktion wird aufgerufen, indem [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver).  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 Diese Funktion wird aufgerufen, um Klassenobjekte zu registrieren.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf das COM-Modul.  
  
 `dwClsContext`  
 Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER. Finden Sie unter [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) Weitere Details.  
  
 `dwFlags`  
 Bestimmt die Verbindungstypen auf das Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE. Finden Sie unter [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (veraltete Elemente in ATL 7.0) und [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 Diese Funktion wird aufgerufen, um eine oder mehrere Klassenfactorys aus der ROT (Running Object Table) zu entfernen.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>Parameter  
 `pComModule`  
 Ein Zeiger auf das COM-Modul.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (veraltete Elemente in ATL 7.0) und [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).  
  
##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject  
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
 Ein Zeiger auf das COM-Modul.  
  
 `rclsid`  
 Die CLSID des Objekts erstellt werden.  
  
 `riid`  
 Die IID der angeforderten Schnittstelle.  
  
 `ppv`  
 Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppv` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Hilfsfunktion verwendet, indem [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (veraltete Elemente in ATL 7.0) und [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject).  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
