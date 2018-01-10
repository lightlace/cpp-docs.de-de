---
title: CDebugReportHook Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs: C++
helpviewer_keywords: CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df098ee80bcd8fa81b5503cc21b08ded86945a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook-Klasse
Verwenden Sie diese Klasse wird zum Senden von debugberichten einer named Pipe.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Aufrufe [die SetPipeName](#setpipename), [SetTimeout](#settimeout), und [SetHook](#sethook).|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Aufrufe [CDebugReportHook::RemoveHook](#removehook).|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statisch) Die benutzerdefinierte Berichtsfunktion, die in der C-Laufzeit-Debug-Berichterstellungsprozess verknüpft ist.|  
|[CDebugReportHook::RemoveHook](#removehook)|Rufen Sie diese Methode nicht mehr debugberichten zur named Pipe gesendet und Wiederherstellen der vorherigen Hookfunktion.|  
|[CDebugReportHook::SetHook](#sethook)|Rufen Sie diese Methode zum Starten von debugberichten an der named Pipe gesendet.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Rufen Sie diese Methode zum Festlegen der Computer und der Name der Pipe an die die Debug-Berichte gesendet werden.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie eine Instanz dieser Klasse in der Debug-Builds Ihre Dienste oder Anwendungen zum Senden von debugberichten einer named Pipe. Debug-Berichte werden durch den Aufruf generiert [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) oder über einen Wrapper für diese Funktion z. B. die [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) und [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) Makros.  
  
 Mit dieser Klasse können Sie interaktiv Debuggen von Komponenten, die auf den nicht interaktiven [Fenster Stationen](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Beachten Sie, dass debugberichten gesendet werden, mithilfe des zugrunde liegenden Sicherheitskontexts des Threads. Identitätswechsel ist vorübergehend deaktiviert, sodass debugberichten in Situationen, in dem der Benutzer mit niedrigen Berechtigungen Identitätswechsel, z. B. in Webanwendungen stattfindet, angezeigt werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 Aufrufe [die SetPipeName](#setpipename), [SetTimeout](#settimeout), und [SetHook](#sethook).  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `szMachineName`  
 Der Name des Computers, der die Debugausgabe gesendet werden soll. Der Standardwert ist auf dem lokalen Computer.  
  
 `szPipeName`  
 Der Name der named Pipe an der die Debugausgabe gesendet werden soll.  
  
 `dwTimeout`  
 Die Zeit in Millisekunden an, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 Aufrufe [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 Die benutzerdefinierte Berichtsfunktion, die in der C-Laufzeit-Debug-Berichterstellungsprozess verknüpft ist.  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `reportType`  
 Der Typ des Berichts (_CRT_WARN, _CRT_ERROR oder _CRT_ASSERT).  
  
 `message`  
 Die Meldungszeichenfolge.  
  
 *returnValue*  
 Der Wert, der von zurückgegeben werden soll [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "false" zurück, wenn die Hookfunktion die fragliche Nachricht vollständig verarbeitet, sodass kein weiterer Bericht erforderlich ist. Gibt "true" zurück, wenn `_CrtDbgReport` sollte die Nachricht auf die übliche Weise melden.  
  
### <a name="remarks"></a>Hinweise  
 Die Berichtsfunktion versucht, die named Pipe zu öffnen und die Kommunikation mit dem Prozess am anderen Ende. Wenn die Pipe ausgelastet ist, wird die Berichtsfunktion warten Sie, bis die Pipe kostenlos ist, oder das Timeout abläuft. Das Timeout kann festgelegt werden, von dem Konstruktor oder einen Aufruf von [CDebugReportHook::SetTimeout](#settimeout).  
  
 Der Code in dieser Funktion wird in der zugrunde liegenden Sicherheitskontext des aufrufenden Threads ausgeführt, d. h. Identitätswechsel für die Dauer der diese Funktion deaktiviert ist.  
  
##  <a name="removehook"></a>CDebugReportHook::RemoveHook  
 Rufen Sie diese Methode nicht mehr debugberichten zur named Pipe gesendet und Wiederherstellen der vorherigen Hookfunktion.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) zum Wiederherstellen der vorherigen Hookfunktion.  
  
##  <a name="sethook"></a>CDebugReportHook::SetHook  
 Rufen Sie diese Methode zum Starten von debugberichten an der named Pipe gesendet.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) debugberichten durch weitergeleitet haben [CDebugReportHookProc](#cdebugreporthookproc) zur named Pipe. Diese Klasse der nachverfolgt der vorherigen Hookfunktion, damit es sein kann, wenn wiederhergestellt [RemoveHook](#removehook) aufgerufen wird.  
  
##  <a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Rufen Sie diese Methode zum Festlegen der Computer und der Name der Pipe an die die Debug-Berichte gesendet werden.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Parameter  
 `szMachineName`  
 Der Name des Computers, der die Debugausgabe gesendet werden soll.  
  
 `szPipeName`  
 Der Name der named Pipe an der die Debugausgabe gesendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTimeout`  
 Die Zeit in Millisekunden an, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)
