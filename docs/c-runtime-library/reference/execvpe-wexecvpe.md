---
title: _execvpe _wexecvpe | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execvpe
- _wexecvpe
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
- wexecvpe
- execvpe
- _wexecvpe
- _execvpe
dev_langs: C++
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3c51e9c4247a77d16fe8621ff98b7f3a50f571e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="execvpe-wexecvpe"></a>_execvpe, _wexecvpe
Lädt neue untergeordnete Prozesse und führt sie aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
intptr_t _execvpe(   
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wexecvpe(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cmdname`  
 Pfad der auszuführenden Datei.  
  
 `argv`  
 Array von Zeigern zu Parametern.  
  
 `envp`  
 Array von Zeigern zu Umgebungseinstellungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg kehren diese Funktionen nicht zum aufrufenden Prozess zurück. Ein Rückgabewert "-1" gibt einen Fehler an, in diesem Fall die `errno` (globale Variable) festgelegt ist.  
  
|`errno`-Wert|Beschreibung|  
|-------------------|-----------------|  
|`E2BIG`|Für die Argumente und die Umgebungseinstellungen werden mehr als 32 KB Speicherplatz benötigt.|  
|`EACCES`|Für die angegebene Datei ist eine Sperr- oder Freigabeverletzung aufgetreten.|  
|`EMFILE`|Zu viele Dateien sind geöffnet. (Die angegebene Datei muss geöffnet werden, damit festgestellt werden kann, ob sie ausführbar ist.)|  
|`ENOENT`|Die Datei oder der Pfad wurde nicht gefunden.|  
|`ENOEXEC`|Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.|  
|`ENOMEM`|Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen; der verfügbare Arbeitsspeicher ist beschädigt; oder es ist ein ungültiger Block vorhanden, was darauf hinweist, dass der aufrufende Prozess nicht ordnungsgemäß zugeordnet wurde.|  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen lädt einen neuen Prozess, führt diesen aus und übergibt ein Array von Zeigern auf Befehlszeilenargumente und ein Array von Zeigern auf Umgebungseinstellungen. Diese Funktionen suchen die auszuführende Datei mithilfe der `PATH`-Umgebungsvariable.  
  
 Die `_execvpe`-Funktionen überprüfen ihre Parameter. Wenn `cmdname` ein NULL-Zeiger ist, oder wenn `argv` ein NULL-Zeiger oder ein Zeiger auf ein leeres Array ist, oder wenn das Array als erstes Argument eine leere Zeichenfolge enthält, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben -1 zurück. Es wird kein Prozess gestartet.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------|---------------------|  
|`_execvpe`|\<process.h>|\<errno.h>|  
|`_wexecvpe`|\<process.h> oder \<wchar.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [_exec-, _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)