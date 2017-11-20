---
title: "Debuggen und globale Funktionen für die Fehlerberichterstattung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs: C++
helpviewer_keywords: functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea41febbb9de28ff70d89bfe4f6fcebc9a452ed2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="debugging-and-error-reporting-global-functions"></a>Debuggen und globale Funktionen für die Fehlerberichterstattung
Diese Funktionen geben nützlich, Debuggen und Ablaufverfolgung Einrichtungen.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Gibt eine `GetLastError` in Form eines HRESULT-Fehlercode.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Konvertiert einen Win32-Fehlercode in ein HRESULT.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Richtet **IErrorInfo** Fehlerdetails an einen Client bereitstellen.|  
|["Atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow)|Löst eine `CAtlException` aus.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.|  
  
##  <a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 Gibt den Codewert des letzten Fehlers des aufrufenden Threads in Form eines HRESULT zurück.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Hinweise  
 `AtlHresultFromLastError`Aufrufe `GetLastError` den letzten Fehler abrufen und den Fehler zurück, nach der Konvertierung in ein HRESULT mit der **was zu HRESULT_FROM_WIN32** Makro.  

### <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  

##  <a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Konvertiert einen Win32-Fehlercode in ein HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Parameter  
 *Fehler*  
 Der zu konvertierende Fehlerwert.  
  
### <a name="remarks"></a>Hinweise  
 Konvertiert einen Win32-Fehlercode in ein HRESULT, das mit dem Makro **was zu HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Anstatt **HRESULT_FROM_WIN32(GetLastError())**, verwenden Sie die Funktion [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  

##  <a name="atlreporterror"></a>AtlReportError  
 Richtet die `IErrorInfo` Schnittstelle, um Fehlerinformationen für Clients des Objekts bereitzustellen.  
  
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
 [in] Die CLSID des Objekts, das den Fehler gemeldet.  
  
 `lpszDesc`  
 [in] Die Zeichenfolge, die den Fehler beschreibt. Geben Sie die Unicode-Versionen, die `lpszDesc` ist vom Typ **LPCOLESTR**; die ANSI-Version gibt den Typ des `LPCSTR`.  
  
 `iid`  
 [in] Die IID der Schnittstelle, die den Fehler definieren oder `GUID_NULL` , wenn der Fehler vom Betriebssystem definiert ist.  
  
 `hRes`  
 [in] Die `HRESULT` an den Aufrufer zurückgegeben werden sollen.  
  
 `nID`  
 [in] Der Ressourcenbezeichner, in dem die Zeichenfolge zur fehlerbeschreibung gespeichert ist. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. Debug-Builds ein **ASSERT** führt `nID` eine gültige Zeichenfolge keinen index erstellt. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung auf "Unbekannter Fehler" festgelegt werden  
  
 `dwHelpID`  
 [in] Den Hilfekontextbezeichner für den Fehler.  
  
 `lpszHelpFile`  
 [in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.  
  
 `hInst`  
 [in] Das Handle für die Ressource. Standardmäßig ist dieser Parameter **__AtlBaseModuleModule::GetResourceInstance**, wobei **__AtlBaseModuleModule** wird die globale Instanz von [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) oder einer Klasse daraus abgeleitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die `hRes` Parameter ungleich NULL ist, wird den Wert des `hRes`. Wenn `hRes` ist 0 (null), und klicken Sie dann auf die ersten vier Versionen des `AtlReportError` zurückgeben `DISP_E_EXCEPTION`. Die letzten beiden Versionen zurück, das Ergebnis des Makros **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge *LpszDesc* als die textbeschreibung des Fehlers verwendet wird. Wenn der Client empfängt die `hRes` zurückgegebenen `AtlReportError`, kann der Client zugreifen, die **IErrorInfo** Struktur Einzelheiten zum Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Verwenden Sie keine `AtlReportError` in C++ catch-Handler. Einige überschreibungen von Funktionen verwenden die ATL-Makros zur zeichenfolgenkonvertierung intern, die wiederum die `_alloca` intern funktioniert. Mithilfe von `AtlReportError` in einem C++-Catch Handler kann dazu führen, dass Ausnahmen im Catch-Handler von C++.  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
    
##  <a name="atlthrow"></a>"Atlthrow"  
 Mit dieser Funktion können Sie auf der Grundlage eines `HRESULT`-Statuscodes einen Fehler signalisieren.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Parameter  
 `hr`  
 Standard-HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von ATL und MFC-Code im Falle einer fehlerbedingung. Es kann auch aus Ihrem eigenen Code aufgerufen werden. Die standardmäßige Implementierung dieser Funktion hängt von der Definition des Symbols **_ATL_NO_EXCEPTIONS** und dem Typ des MFC oder ATL-Projekts  
  
 In allen Fällen verfolgt diese Funktion das HRESULT für den Debugger.  
  
 In Visual Studio 2015 Update 3 und höher, wird diese Funktion attributierte __declspec(noreturn) um unbegründete SAL-Warnungen zu vermeiden.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert in einem MFC-Projekt, diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder ein [COleException](../../mfc/reference/coleexception-class.md) basierend auf dem Wert von HRESULT.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht in einem ATL-Projekt, löst die Funktion definiert einen [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Wenn **_ATL_NO_EXCEPTIONS** wird definiert, die Funktion wird ein Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.  
  
 Für ATL-Projekte ist es möglich, geben Sie Ihre eigene Implementierung dieser Funktion von ATL, die im Fall eines Fehlers verwendet werden. Zu diesem Zweck definieren Sie Ihre eigene Funktion mit der gleichen Signatur wie `AtlThrow` und #define `AtlThrow` werden der Name der Funktion. Dies muss vor dem Einfügen von atlexcept.h (d. h. es durchgeführt werden muss, bevor die ATL-Header einschließen, da atlbase.h atlexcept.h umfasst) erfolgen. Attribut Ihrer Funktion `__declspec(noreturn)` um unbegründete SAL-Warnungen zu vermeiden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  

##  <a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt eine Ablaufverfolgung für das Ergebnis des `GetLastError` an den Debugger.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht definiert in einem MFC-Projekt, diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder ein [COleException](../../mfc/reference/coleexception-class.md) basierend auf den Rückgabewert von `GetLastError`.  
  
 Wenn **_ATL_NO_EXCEPTIONS** ist nicht in einem ATL-Projekt, löst die Funktion definiert einen [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Wenn **_ATL_NO_EXCEPTIONS** wird definiert, die Funktion wird ein Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  
   
     
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Debuggen und Fehlerberichterstattungs-Makros](../../atl/reference/debugging-and-error-reporting-macros.md)









