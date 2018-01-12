---
title: system, _wsystem | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- system
- _wsystem
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tsystem
- _wsystem
dev_langs: C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c470717d48836fd405e98f5fccca222e87a9c33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="system-wsystem"></a>system, _wsystem
Führt einen Befehl aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `command`  
 Der Befehl, der ausgeführt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich 0 zurück, wenn `command` auf `NULL` festgelegt ist und der Befehlsinterpreter gefunden wird. Gibt 0 zurück und legt `errno` auf `ENOENT` fest, wenn kein Befehlsinterpreter gefunden wird. `system` gibt den vom Befehlsinterpreter zurückgegebenen Wert zurück, wenn `command` nicht `NULL` ist. Gibt den Wert 0 nur zurück, wenn der Befehlsinterpreter den Wert 0 zurückgibt. Ein Rückgabewert von – 1 zeigt einen Fehler, und `errno` auf einen der folgenden Werte festgelegt:  
  
 `E2BIG`  
 Die Argumentliste (systemabhängig) ist zu groß.  
  
 `ENOENT`  
 Der Befehlsinterpreter kann nicht gefunden werden.  
  
 `ENOEXEC`  
 Die Befehlsinterpreterdatei kann nicht ausgeführt werden, da das Format ungültig ist.  
  
 `ENOMEM`  
 Es ist nicht genügend Arbeitsspeicher verfügbar, um den Befehl auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.  
  
 Weitere Informationen zu diesen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `system`-Funktion übergibt `command` an den Befehlsinterpreter, der die Zeichenfolge als Betriebssystembefehl ausführt. `system` verwendet die `COMSPEC`- und `PATH`-Umgebungsvariablen, um nach der Befehlsinterpreterdatei CMD.exe zu suchen. Wenn `command` auf `NULL` festgelegt ist, überprüft die Funktion lediglich, ob der Befehlsinterpreter vorhanden ist.  
  
 Vor dem Aufruf von `system` müssen Sie jeden Stream explizit leeren, mithilfe von `fflush`, oder explizit schließen, mithilfe von `_flushall`.  
  
 `_wsystem` ist eine Breitzeichenversion von `system`. Das `command`-Argument für `_wsystem` ist eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`system`|\<process.h> oder\<stdlib.h>|  
|`_wsystem`|\<process.h> oder \<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `system` zum Eingeben einer Textdatei verwendet.  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## <a name="input-crtsystemtxt"></a>Input: crt_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [_exec-, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)