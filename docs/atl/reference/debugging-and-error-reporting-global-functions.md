---
title: Debuggen und globale Funktionen für die Fehlerberichterstattung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bef300671894e054ddf9b1ca0ab9dcf3b135370
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019414"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Debuggen und globale Funktionen für die Fehlerberichterstattung

Diese Funktionen bieten nützliche Funktionen zum Debuggen und Ablaufverfolgung.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Gibt eine `GetLastError` in Form eines HRESULT-Fehlercode.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Konvertiert einen Win32-Fehlercode in ein HRESULT.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Richtet `IErrorInfo` Fehlerdetails an einen Client bereitstellen.|
|["Atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow)|Löst eine `CAtlException` aus.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.|

##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError

Gibt den Codewert des letzten Fehlers des aufrufenden Threads in Form eines HRESULT zurück.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Hinweise

`AtlHresultFromLastError` Aufrufe `GetLastError` zum letzten Fehler abrufen und der Fehler nach der Konvertierung in ein HRESULT, der mit dem Makro was zu HRESULT_FROM_WIN32 zurückgegeben.  

### <a name="requirements"></a>Anforderungen

**Header:** "atlcomcli.h"  

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32

Konvertiert einen Win32-Fehlercode in ein HRESULT.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Parameter

*Fehler*<br/>
Der Wert des Fehlercodes zu konvertieren.

### <a name="remarks"></a>Hinweise

Konvertiert einen Win32-Fehlercode in ein HRESULT, das mit dem Makro was zu HRESULT_FROM_WIN32 an.

> [!NOTE]
>  Anstelle von `HRESULT_FROM_WIN32(GetLastError())`, verwenden Sie die Funktion [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Anforderungen

**Header:** "atlcomcli.h"  

##  <a name="atlreporterror"></a>  AtlReportError

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

*clsid*<br/>
[in] Die CLSID des Objekts der Fehler wird gemeldet.

*lpszDesc*<br/>
[in] Die Zeichenfolge, die den Fehler beschreibt. Die Unicode-Versionen angeben, die *LpszDesc* ist vom Typ LPCOLESTR; die ANSI-Version gibt einen Typ LPCSTR.

*IID*<br/>
[in] Die IID der Schnittstelle, die den Fehler oder die GUID_NULL definieren, wenn der Fehler vom Betriebssystem definiert ist.

*' hres '*<br/>
[in] Das HRESULT, Sie möchten, die an den Aufrufer zurückgegeben werden.

*nID*<br/>
[in] Der Ressourcenbezeichner, in dem die Zeichenfolge zur fehlerbeschreibung gespeichert ist. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. In Debugbuilds einer **ASSERT** führt, wenn *nID* indiziert sich nicht auf eine gültige Zeichenfolge. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung festgelegt, "Unbekannter Fehler."

*dwHelpID*<br/>
[in] Den Hilfekontextbezeichner für den Fehler.

*lpszHelpFile*<br/>
[in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.

*hInst*<br/>
[in] Das Handle für die Ressource. Standardmäßig ist dieser Parameter `__AtlBaseModuleModule::GetResourceInstance`, wobei `__AtlBaseModuleModule` ist die globale Instanz des [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) oder eine Klasse abgeleitet wird.

### <a name="return-value"></a>Rückgabewert

Wenn die *' hres '* Parameter ungleich NULL ist, wird den Wert des *' hres '*. Wenn *' hres '* ist 0 (null), und klicken Sie dann auf die ersten vier Versionen von `AtlReportError` DISP_E_EXCEPTION zurück. Die letzten beiden Versionen Zurückgeben des Ergebnisses des Makros **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge *LpszDesc* als die textbeschreibung des Fehlers verwendet wird. Wenn der Client empfängt die *' hres '* Sie zurückgeben `AtlReportError`, kann der Client zugreifen, die `IErrorInfo` Struktur für die Details zu diesem Fehler.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
>  Verwenden Sie keine `AtlReportError` in C++-catch-Handler. Einige überschreibungen von dieser Funktionen verwenden die ATL-Zeichenfolgen-konvertierungsmakros intern die verwenden, die wiederum die `_alloca` intern funktionieren. Mithilfe von `AtlReportError` in einem C++-Catch Handler kann dazu führen, dass Ausnahmen in C++-Catch-Handler.  

### <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="atlthrow"></a>  "Atlthrow"

Rufen Sie diese Funktion, um einen Fehler, die basierend auf einen Statuscode "HRESULT" signalisieren.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Parameter

*HR*<br/>
Standard-HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Diese Funktion wird von ATL- und MFC-Code im Falle einer fehlerbedingung verwendet. Es kann auch über Ihren eigenen Code aufgerufen werden. Die Standardimplementierung dieser Funktion hängt davon ab, die Definition der Symbol-_ATL_NO_EXCEPTIONS und für den Typ des MFC- oder ATL-Projekts

In allen Fällen verfolgt diese Funktion das HRESULT für den Debugger an.

In Visual Studio 2015 Update 3 und höher ist diese Funktion attributierte __declspec(noreturn), falsche SAL-Warnungen zu vermeiden.

Wenn _ATL_NO_EXCEPTIONS nicht in einem MFC-Projekt definiert ist, wird diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md) basierend auf dem Wert von HRESULT.

Wenn _ATL_NO_EXCEPTIONS nicht in einem ATL-Projekt definiert ist, löst die Funktion eine [CAtlException](../../atl/reference/catlexception-class.md).

Wenn _ATL_NO_EXCEPTIONS definiert ist, wird ein Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.

Bei ATL-Projekten ist es möglich, geben Sie Ihre eigene Implementierung dieser Funktion, die bei einem Ausfall von ATL verwendet werden. Zu diesem Zweck definieren Sie Ihre eigene Funktion mit der gleichen Signatur wie `AtlThrow` und #define `AtlThrow` den Namen Ihrer Funktion sein. Dies muss erfolgen, bevor einschließlich atlexcept.h (d. h., dass es erfolgen muss, bevor ATL-Header einschließen, da atlbase.h atlexcept.h enthält). Ihre Funktion Attribut `__declspec(noreturn)` , falsche SAL-Warnungen zu vermeiden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Anforderungen

**Header:** atldef.h  

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32

Mit dieser Funktion können Sie auf der Grundlage des Ergebnisses der Windows-Funktion `GetLastError` einen Fehler signalisieren.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Hinweise

Diese Funktion führt eine Ablaufverfolgung für das Ergebnis des `GetLastError` an den Debugger.

Wenn _ATL_NO_EXCEPTIONS nicht in einem MFC-Projekt definiert ist, wird diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md) basierend auf den Rückgabewert von `GetLastError`.

Wenn _ATL_NO_EXCEPTIONS nicht in einem ATL-Projekt definiert ist, löst die Funktion eine [CAtlException](../../atl/reference/catlexception-class.md).

Wenn _ATL_NO_EXCEPTIONS definiert ist, wird ein Assertionsfehler ausgelöst, anstatt eine Ausnahme auszulösen.  

## <a name="requirements"></a>Anforderungen

**Header:** atldef.h

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)<br/>
[Debuggen und Fehlerberichterstattungs-Makros](../../atl/reference/debugging-and-error-reporting-macros.md)

