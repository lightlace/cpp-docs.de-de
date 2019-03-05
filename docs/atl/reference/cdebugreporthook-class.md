---
title: CDebugReportHook-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: a7c5993d1b96daaa73e7fc9509c93e66daed77f3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262453"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook-Klasse

Verwenden Sie diese Klasse zum Senden von debugberichten und einer named Pipe an.

## <a name="syntax"></a>Syntax

```
class CDebugReportHook
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Aufrufe [die SetPipeName](#setpipename), [SetTimeout](#settimeout), und [SetHook](#sethook).|
|[CDebugReportHook::~CDebugReportHook](#dtor)|Calls [CDebugReportHook::RemoveHook](#removehook).|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statisch) Reporting-Prozess debuggen, die benutzerdefinierte Berichtsfunktion, die in der C-Laufzeit verknüpft wird.|
|[CDebugReportHook::RemoveHook](#removehook)|Rufen Sie diese Methode zum Beenden von debugberichten an der named Pipe senden und Wiederherstellen der vorherigen Hookfunktion.|
|[CDebugReportHook::SetHook](#sethook)|Rufen Sie diese Methode zum Senden debugberichten an der named Pipe an.|
|[CDebugReportHook::SetPipeName](#setpipename)|Rufen Sie diese Methode, um festzulegen, den Computer und der Name der Pipe an die die Debug-Berichte gesendet werden.|
|[CDebugReportHook::SetTimeout](#settimeout)|Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.|

## <a name="remarks"></a>Hinweise

Erstellen Sie eine Instanz dieser Klasse im Debug-Builds für Ihre Dienste oder Anwendungen zum Senden von debugberichten und einer named Pipe an. Debug-Berichte werden generiert, durch den Aufruf [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) oder über einen Wrapper für diese Funktion z. B. die [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) und [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) Makros.

Verwendung dieser Klasse können Sie interaktiv Debuggen von Komponenten, die im nicht interaktiven [Fenster Stationen](/windows/desktop/winstation/window-stations).

Beachten Sie, dass debugberichten gesendet werden, mithilfe des zugrunde liegenden Sicherheitskontexts des Threads. Identitätswechsel wird vorübergehend deaktiviert, sodass debugberichten in Situationen angezeigt werden können, in dem Identitätswechsel von Benutzern mit geringen Rechten, wie z. B. in Webanwendungen stattfindet.

## <a name="requirements"></a>Anforderungen

**Header:** atlutil.h

##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook

Aufrufe [die SetPipeName](#setpipename), [SetTimeout](#settimeout), und [SetHook](#sethook).

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Parameter

*szMachineName*<br/>
Der Name des Computers, der die Debugausgabe gesendet werden soll. Der Standardwert ist auf dem lokalen Computer.

*szPipeName*<br/>
Der Name der named Pipe an die die Debugausgabe gesendet werden soll.

*dwTimeout*<br/>
Die Zeit in Millisekunden an, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.

##  <a name="dtor"></a>  CDebugReportHook:: ~ CDebugReportHook

Calls [CDebugReportHook::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc

Reporting-Prozess debuggen, die benutzerdefinierte Berichtsfunktion, die in der C-Laufzeit verknüpft wird.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Der Typ des Berichts (_CRT_WARN, _CRT_ERROR oder _CRT_ASSERT).

*message*<br/>
Die Meldungszeichenfolge.

*returnValue*<br/>
Der Wert, der von zurückgegeben werden sollen [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).

### <a name="return-value"></a>Rückgabewert

Gibt "false" zurück, wenn der Hook betreffende Meldung vollständig verarbeitet, sodass kein weiterer Bericht erforderlich ist. Gibt "true" zurück, wenn `_CrtDbgReport` sollte die Nachricht auf die übliche Weise melden.

### <a name="remarks"></a>Hinweise

Die Berichtsfunktion versucht, die named Pipe zu öffnen und die Kommunikation mit der Prozess am anderen Ende. Wenn die Pipe beschäftigt ist, wartet die Berichtsfunktion, bis die Pipe kostenlos ist, oder das Timeout abläuft. Das Timeout kann festgelegt werden, durch den Konstruktor oder einen Aufruf von [CDebugReportHook::SetTimeout](#settimeout).

Der Code in dieser Funktion wird in der zugrunde liegenden Sicherheitskontext des aufrufenden Threads ausgeführt, d. h. der Identitätswechsel für die Dauer dieser Funktion deaktiviert ist.

##  <a name="removehook"></a>  CDebugReportHook::RemoveHook

Rufen Sie diese Methode zum Beenden von debugberichten an der named Pipe senden und Wiederherstellen der vorherigen Hookfunktion.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>Hinweise

Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) zum Wiederherstellen der vorherigen Hookfunktion.

##  <a name="sethook"></a>  CDebugReportHook::SetHook

Rufen Sie diese Methode zum Senden debugberichten an der named Pipe an.

```
void SetHook() throw();
```

### <a name="remarks"></a>Hinweise

Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) debugberichten durch weitergeleitet haben [CDebugReportHookProc](#cdebugreporthookproc) auf die named Pipe. Diese Klasse verfolgt des der vorherigen Hookfunktion, damit es sein kann, wenn wiederhergestellt [RemoveHook](#removehook) aufgerufen wird.

##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName

Rufen Sie diese Methode, um festzulegen, den Computer und der Name der Pipe an die die Debug-Berichte gesendet werden.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Parameter

*szMachineName*<br/>
Der Name des Computers, der die Debugausgabe gesendet werden soll.

*szPipeName*<br/>
Der Name der named Pipe an die die Debugausgabe gesendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout

Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Parameter

*dwTimeout*<br/>
Die Zeit in Millisekunden an, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.

## <a name="see-also"></a>Siehe auch

[Klassen](../../atl/reference/atl-classes.md)
