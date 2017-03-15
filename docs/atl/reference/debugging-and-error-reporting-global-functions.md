---
title: Debuggen von Fehlern sowie globale Funktionen | Microsoft-Dokumentation
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
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4a412910d13d10606080c14412d33d2b614fdcec
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>Debuggen und globale Funktionen für die Fehlerberichterstattung
Diese Funktionen stellen nützliche Debug- und Trace-Funktionen.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)|Gibt eine `GetLastError` in Form eines HRESULT-Fehlercode.|  
|[AtlHresultFromWin32](http://msdn.microsoft.com/library/63add2dd-274c-4e72-a98c-040b93413a2f)|Konvertiert einen Win32-Fehlercode in ein HRESULT.|  
|[AtlReportError](http://msdn.microsoft.com/library/86b046a5-ea18-4ecf-9aab-40fc1eab847c)|Richtet **IErrorInfo** Fehlerdetails an einen Client bereitstellen.|  
|[AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)|Löst eine `CAtlException` aus.|  
|[AtlThrowLastWin32](http://msdn.microsoft.com/library/8bce8e56-c7cd-4ebb-8c62-80ebc63a3d07)|Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.|  
  
##  <a name="a-nameatlhresultfromlasterrora--atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 Gibt den Codewert des letzten Fehlers des aufrufenden Threads in Form eines HRESULT zurück.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Hinweise  
 `AtlHresultFromLastError`Aufrufe `GetLastError` den letzten Fehler abrufen und den Fehler zurück, nach der Konvertierung in ein HRESULT mit der **was zu HRESULT_FROM_WIN32** Makro.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlcomcli.h  

##  <a name="a-nameatlhresultfromwin32a--atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Konvertiert einen Win32-Fehlercode in ein HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Parameter  
 *Fehler*  
 Der Wert des Fehlercodes zu konvertieren.  
  
### <a name="remarks"></a>Hinweise  
 Konvertiert einen Win32-Fehlercode in ein HRESULT, das mit dem Makro **was zu HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Anstelle von **HRESULT_FROM_WIN32(GetLastError())**, verwenden Sie die Funktion [AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66).  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlcomcli.h  

##  <a name="a-nameatlreporterrora--atlreporterror"></a><a name="atlreporterror"></a>AtlReportError  
 Richtet die `IErrorInfo` -Schnittstelle zur Bereitstellung von Fehlerinformationen für Clients des Objekts.  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID des Objekts, das den Fehler meldet.  
  
 `lpszDesc`  
 [in] Die Zeichenfolge, die den Fehler beschreibt. Die Unicode-Versionen angeben, `lpszDesc` ist vom Typ **LPCOLESTR**; die ANSI-Version gibt den Typ des `LPCSTR`.  
  
 `iid`  
 [in] Die IID für die Schnittstelle, die den Fehler definieren oder `GUID_NULL` , wenn der Fehler vom Betriebssystem definiert ist.  
  
 `hRes`  
 [in] Die `HRESULT` an den Aufrufer zurückgegeben werden sollen.  
  
 `nID`  
 [in] Der Ressourcenbezeichner, wo die Fehlerbeschreibungszeichenfolge gespeichert werden. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. In Debugbuilds eine **ASSERT** führt, wenn `nID` nicht indizieren, eine gültige Zeichenfolge. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung festgelegt auf "Ein Fehler aufgetreten."  
  
 `dwHelpID`  
 [in] Den Hilfekontextbezeichner für den Fehler.  
  
 `lpszHelpFile`  
 [in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.  
  
 `hInst`  
 [in] Das Handle für die Ressource. Dieser Parameter ist standardmäßig **__AtlBaseModuleModule::GetResourceInstance**, wobei **__AtlBaseModuleModule** ist die globale Instanz von [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) oder eine Klasse abgeleitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die `hRes` Parameter ungleich NULL ist, gibt den Wert der `hRes`. Wenn `hRes` ist&0; (null), und klicken Sie dann auf die ersten vier Versionen von `AtlReportError` zurückgeben `DISP_E_EXCEPTION`. Die letzten beiden Versionen zurück, das Ergebnis des Makros **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge *LpszDesc* als der Beschreibung des Fehlers verwendet wird. Erhält der Client die `hRes` zurückgegebenen `AtlReportError`, kann der Client zugreifen, die **IErrorInfo** Struktur für die Einzelheiten zu dem Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&52;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Verwenden Sie keine `AtlReportError` in C++-catch-Handler. Einige überschreibt dieser Funktionen verwenden die ATL-zeichenfolgenkonvertierungsmakros intern, die wiederum die `_alloca` intern funktionieren. Mithilfe von `AtlReportError` in einem C++-Catch Handler kann dazu führen, dass Ausnahmen in C++-Catch-Handler.  

### <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
    
##  <a name="a-nameatlthrowa--atlthrow"></a><a name="atlthrow"></a>AtlThrow  
 Mit dieser Funktion können Sie auf der Grundlage eines `HRESULT`-Statuscodes einen Fehler signalisieren.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Parameter  
 `hr`  
 Standard-HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von ATL- und MFC-Code im Falle eines Fehlerzustands verwendet. Es kann auch aus Ihrem eigenen Code aufgerufen werden. Die standardmäßige Implementierung dieser Funktion hängt von der Definition des Symbols **_ATL_NO_EXCEPTIONS** und auf dem Typ von MFC oder ATL-Projekt  
  
 In allen Fällen verfolgt diese Funktion das HRESULT für den Debugger.  
  
 In Visual Studio 2015 Update 3 oder höher, wird diese Funktion attributierte __declspec(noreturn), falsche SAL-Warnungen zu vermeiden.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert in einem MFC-Projekt, löst diese Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md) basierend auf dem Wert von HRESULT.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert, in einem ATL-Projekt die Funktion löst einen [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Wenn **_ATL_NO_EXCEPTIONS** wird definiert, die Funktion wird eine Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.  
  
 Für ATL-Projekte ist es möglich, eigene Implementierung dieser Funktion von ATL bei Auftreten eines Fehlers verwendet werden. Definieren Sie hierzu eine eigene Funktion mit der gleichen Signatur wie `AtlThrow` und #define `AtlThrow` werden der Name der Funktion. Dies muss erfolgen, bevor einschließlich atlexcept.h (d. h., es durchgeführt werden muss, bevor einschließlich ATL-Headern, da atlbase.h atlexcept.h enthält). Attribut die Funktion `__declspec(noreturn)` , falsche SAL-Warnungen zu vermeiden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#95;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  

##  <a name="a-nameatlthrowlastwin32a--atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zeichnet das Ergebnis des `GetLastError` an den Debugger.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert in einem MFC-Projekt, löst diese Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md) basierend auf den Rückgabewert von `GetLastError`.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert, in einem ATL-Projekt die Funktion löst einen [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Wenn **_ATL_NO_EXCEPTIONS** wird definiert, die Funktion wird eine Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  
   
     
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Debuggen und die Fehlerberichterstattung Makros](../../atl/reference/debugging-and-error-reporting-macros.md)










