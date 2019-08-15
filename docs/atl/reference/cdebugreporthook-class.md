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
ms.openlocfilehash: 7187448b2ba2c9d3ab0399aa3e75ce8d757bfec1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496774"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook-Klasse

Verwenden Sie diese Klasse, um Debugberichte an einen Named Pipe zu senden.

## <a name="syntax"></a>Syntax

```
class CDebugReportHook
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Ruft [setpitzame](#setpipename), [setTimeout](#settimeout)und [sethook](#sethook)auf.|
|[CDebugReportHook::~CDebugReportHook](#dtor)|Ruft [CDebugReportHook:: RemoveHook](#removehook)auf.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|Kum Die benutzerdefinierte Berichtsfunktion, die mit dem Debug-Bericht Erstellungs Prozess der C-Laufzeit verknüpft ist.|
|[CDebugReportHook::RemoveHook](#removehook)|Mit dieser Methode können Sie keine Debugberichte an den Named Pipe senden und den vorherigen berichtshook wiederherstellen.|
|[CDebugReportHook::SetHook](#sethook)|Mit dieser Methode beginnen Sie mit dem Senden von debugberichten an den Named Pipe.|
|[CDebugReportHook::SetPipeName](#setpipename)|Mit dieser Methode können Sie den Computer und den Namen der Pipe festlegen, an die die Debugberichte gesendet werden.|
|[CDebugReportHook::SetTimeout](#settimeout)|Mit dieser Methode können Sie die Zeit in Millisekunden festlegen, die diese Klasse wartet, bis die Named Pipe verfügbar wird.|

## <a name="remarks"></a>Hinweise

Erstellen Sie eine Instanz dieser Klasse in Debugbuilds ihrer Dienste oder Anwendungen, um Debugberichte an einen Named Pipe zu senden. Debugberichte werden durch Aufrufen von [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) oder mithilfe eines Wrappers für diese Funktion generiert, wie z. b. die Makros [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) und [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) .

Mit dieser Klasse können Sie Komponenten, die in nicht interaktiven [Fenster Stationen](/windows/win32/winstation/window-stations)ausgeführt werden, interaktiv Debuggen.

Beachten Sie, dass Debugberichte mithilfe des zugrunde liegenden Sicherheits Kontexts des Threads gesendet werden. Der Identitätswechsel ist vorübergehend deaktiviert, sodass Debugberichte in Situationen angezeigt werden können, in denen der Identitätswechsel von Benutzern mit geringen Rechten stattfindet, z. b. in Webanwendungen.

## <a name="requirements"></a>Anforderungen

**Header:** atlutil. h

##  <a name="cdebugreporthook"></a>CDebugReportHook:: CDebugReportHook

Ruft [setpitzame](#setpipename), [setTimeout](#settimeout)und [sethook](#sethook)auf.

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Parameter

*szMachineName*<br/>
Der Name des Computers, an den die Debug-Ausgabe gesendet werden soll. Der Standardwert ist der lokale Computer.

*szPipeName*<br/>
Der Name des Named Pipe, an das die Debugausgabe gesendet werden soll.

*dwTimeout*<br/>
Die Zeit in Millisekunden, die diese Klasse wartet, bis die Named Pipe verfügbar wird.

##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook

Ruft [CDebugReportHook:: RemoveHook](#removehook)auf.

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>CDebugReportHook:: cdebugreporthookproc

Die benutzerdefinierte Berichtsfunktion, die mit dem Debug-Bericht Erstellungs Prozess der C-Laufzeit verknüpft ist.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Der Berichtstyp (_CRT_WARN, _CRT_ERROR oder _CRT_ASSERT).

*message*<br/>
Die Meldungs Zeichenfolge.

*returnValue*<br/>
Der Wert, der von [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt false zurück, wenn der Hook die fragliche Nachricht vollständig verarbeitet, sodass keine weitere Berichterstellung erforderlich ist. Gibt true zurück `_CrtDbgReport` , wenn die Meldung auf die normale Weise melden soll.

### <a name="remarks"></a>Hinweise

Die Berichterstattungs Funktion versucht, die Named Pipe zu öffnen und mit dem Prozess am anderen Ende zu kommunizieren. Wenn die Pipe ausgelastet ist, wartet die Berichterstattungs Funktion, bis die Pipe frei ist oder das Timeout abläuft. Das Timeout kann durch den Konstruktor oder durch einen [CDebugReportHook:: setTimeout](#settimeout)-Wert festgelegt werden.

Der Code in dieser Funktion wird im zugrunde liegenden Sicherheitskontext des aufrufenden Threads ausgeführt, d. h., der Identitätswechsel ist für die Dauer dieser Funktion deaktiviert.

##  <a name="removehook"></a>CDebugReportHook:: RemoveHook

Mit dieser Methode können Sie keine Debugberichte an den Named Pipe senden und den vorherigen berichtshook wiederherstellen.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>Hinweise

Ruft [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) auf, um den vorherigen berichtshook wiederherzustellen.

##  <a name="sethook"></a>CDebugReportHook:: abkthook

Mit dieser Methode beginnen Sie mit dem Senden von debugberichten an den Named Pipe.

```
void SetHook() throw();
```

### <a name="remarks"></a>Hinweise

Ruft [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) auf, damit Debugberichte durch [cdebugreporthookproc](#cdebugreporthookproc) an die Named Pipe weitergeleitet werden. Mit dieser Klasse wird der vorherige berichtshook nachverfolgt, sodass er wieder hergestellt werden kann, wenn [RemoveHook](#removehook) aufgerufen wird.

##  <a name="setpipename"></a>CDebugReportHook:: setpipoame

Mit dieser Methode können Sie den Computer und den Namen der Pipe festlegen, an die die Debugberichte gesendet werden.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Parameter

*szMachineName*<br/>
Der Name des Computers, an den die Debug-Ausgabe gesendet werden soll.

*szPipeName*<br/>
Der Name des Named Pipe, an das die Debugausgabe gesendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="settimeout"></a>CDebugReportHook:: setTimeout

Mit dieser Methode können Sie die Zeit in Millisekunden festlegen, die diese Klasse wartet, bis die Named Pipe verfügbar wird.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Parameter

*dwTimeout*<br/>
Die Zeit in Millisekunden, die diese Klasse wartet, bis die Named Pipe verfügbar wird.

## <a name="see-also"></a>Siehe auch

[Klassen](../../atl/reference/atl-classes.md)
