---
title: _execlpe, _wexeclpe | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execlpe
- _wexeclpe
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wexeclpe
- execlpe
- wexeclpe
- _execlpe
dev_langs: C++
helpviewer_keywords:
- wexeclpe function
- _wexeclpe function
- _execlpe function
- execlpe function
ms.assetid: 07b861da-3e7e-4f1d-bb80-ad69b55e5162
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 488db0ebbc44265c2be35dcdcb6995c05d7b8a10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="execlpe-wexeclpe"></a>_execlpe, _wexeclpe
Lädt neue untergeordnete Prozesse und führt sie aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
intptr_t _execlpe(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexeclpe(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cmdname`  
 Pfad der auszuführenden Datei.  
  
 `arg0, ... argn`  
 Liste von Zeigern zu Parametern.  
  
 `envp`  
 Array von Zeigern zu Umgebungseinstellungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg kehren diese Funktionen nicht zum aufrufenden Prozess zurück. Ein Rückgabewert "-1" gibt einen Fehler an, in diesem Fall die `errno` (globale Variable) festgelegt ist.  
  
|`errno`-Wert|Beschreibung|  
|-------------------|-----------------|  
|`E2BIG`|Für die Argumente und die Umgebungseinstellungen werden mehr als 32 KB Speicherplatz benötigt.|  
|`EACCES`|Für die angegebene Datei ist eine Sperr- oder Freigabeverletzung aufgetreten.|  
|`EINVAL`|Ungültiger Parameter.|  
|`EMFILE`|Zu viele Dateien geöffnet (die angegebene Datei muss geöffnet werden, damit festgestellt werden kann, ob sie ausführbar ist).|  
|`ENOENT`|Die Datei oder der Pfad wurde nicht gefunden.|  
|`ENOEXEC`|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.|  
|`ENOMEM`|Es ist nicht genügend Arbeitsspeicher, um den neuen Prozess auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.|  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen erstellt einen neuen Prozess und führt diesen aus, übergibt jedes Befehlszeilenargument als separaten Parameter und übergibt außerdem ein Array von Zeigern auf die Umgebungseinstellungen. Diese Funktionen suchen die auszuführende Datei mithilfe der `PATH`-Umgebungsvariable.  
  
 Die `_execlpe`-Funktionen überprüfen ihre Parameter. Wenn entweder `cmdname` oder `arg0` ein NULL-Zeiger oder eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben -1 zurück. Es wird kein neuer Prozess gestartet.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------|---------------------|  
|`_execlpe`|\<process.h>|\<errno.h>|  
|`_wexeclpe`|\<process.h> oder \<wchar.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [_exec-, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [_exec, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)