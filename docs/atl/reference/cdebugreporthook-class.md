---
title: CDebugReportHook Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
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
ms.openlocfilehash: 632167d4f78ef930673450d6d087f32e91b6541f
ms.lasthandoff: 02/24/2017

---
# <a name="cdebugreporthook-class"></a>CDebugReportHook-Klasse
Verwenden Sie diese Klasse Debug-Berichte mit einer named Pipe zu senden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Aufrufe [die SetPipeName](#setpipename), [SetTimeout](#settimeout), und [SetHook](#sethook).|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Aufrufe [CDebugReportHook::RemoveHook](#removehook).|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statisch) Die benutzerdefinierte Berichtsfunktion, die in den C-Laufzeit-Debug verknüpft ist.|  
|[CDebugReportHook::RemoveHook](#removehook)|Rufen Sie diese Methode zum Beenden, Debuggen die named Pipe senden und Wiederherstellen der vorherigen Hookfunktion.|  
|[CDebugReportHook::SetHook](#sethook)|Rufen Sie diese Methode zum Starten des Debuggen mit der named Pipe senden.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Rufen Sie diese Methode zum Festlegen der Computer und der Name der Pipe, die die Debug-Berichte gesendet werden.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie eine Instanz dieser Klasse im Debug-Builds Ihrer Dienste oder Programme Debug-Berichte mit einer named Pipe zu senden. Debug-Berichten werden durch Aufrufen von [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) oder über einen Wrapper für diese Funktion z. B. die [ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e) und [ATLASSERT](http://msdn.microsoft.com/library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) Makros.  
  
 Mit dieser Klasse können Sie interaktiv Debuggen von Komponenten, die im nicht interaktiven [Arbeitsstationen](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Beachten Sie, dass Debuggen Sendung von Berichten mithilfe des zugrunde liegenden Sicherheitskontexts des Threads. Identitätswechsel ist vorübergehend deaktiviert, sodass Debug-Berichte in Situationen angezeigt werden können, wo Identitätswechsel von Benutzern mit eingeschränkten Berechtigungen, z. B. in ASP.NET-Webanwendungen stattfindet.  
  
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
 Der Name des Computers, an den die Debugausgabe gesendet werden soll. Der Standardwert ist auf dem lokalen Computer.  
  
 `szPipeName`  
 Der Name der named Pipe an der die Debugausgabe gesendet werden soll.  
  
 `dwTimeout`  
 Die Zeit in Millisekunden, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 Aufrufe [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 Die benutzerdefinierte Berichtsfunktion, die in den C-Laufzeit-Debug verknüpft ist.  
  
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
 Der Wert, der zurückgegeben werden sollen [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt FALSE zurück, wenn die Hookfunktion betreffende Meldung vollständig bearbeitet, sodass kein weiterer Bericht erforderlich ist. Gibt TRUE zurück, wenn `_CrtDbgReport` sollte die Nachricht auf die übliche Weise melden.  
  
### <a name="remarks"></a>Hinweise  
 Die Berichtsfunktion versucht, die named Pipe zu öffnen und die Kommunikation mit dem Prozess am anderen Ende. Wenn die Pipe ausgelastet ist, wird die Berichtsfunktion warten, bis die Pipe kostenlos ist oder das Timeout abläuft. Das Timeout kann festgelegt werden, durch den Konstruktor oder einen Aufruf von [CDebugReportHook::SetTimeout](#settimeout).  
  
 Der Code in dieser Funktion wird in der zugrunde liegenden Sicherheitskontext des aufrufenden Threads ausgeführt, d. h. Identitätswechsel für die Dauer dieser Funktion deaktiviert ist.  
  
##  <a name="removehook"></a>CDebugReportHook::RemoveHook  
 Rufen Sie diese Methode zum Beenden, Debuggen die named Pipe senden und Wiederherstellen der vorherigen Hookfunktion.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) zum Wiederherstellen der vorherigen Hookfunktion.  
  
##  <a name="sethook"></a>CDebugReportHook::SetHook  
 Rufen Sie diese Methode zum Starten des Debuggen mit der named Pipe senden.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) Debug Berichte über weitergeleitet haben [CDebugReportHookProc](#cdebugreporthookproc) der named Pipe. Diese Klasse speichert die vorherigen Hookfunktion, sodass des sein kann wiederhergestellt, wenn [RemoveHook](#removehook) aufgerufen wird.  
  
##  <a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Rufen Sie diese Methode zum Festlegen der Computer und der Name der Pipe, die die Debug-Berichte gesendet werden.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Parameter  
 `szMachineName`  
 Der Name des Computers, an den die Debugausgabe gesendet werden soll.  
  
 `szPipeName`  
 Der Name der named Pipe an der die Debugausgabe gesendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Rufen Sie diese Methode, um die Zeit in Millisekunden festgelegt, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Parameter  
 `dwTimeout`  
 Die Zeit in Millisekunden, dass diese Klasse wartet, für die benannte Pipe verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)

