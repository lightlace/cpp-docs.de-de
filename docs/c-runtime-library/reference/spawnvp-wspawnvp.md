---
title: _spawnvp, _wspawnvp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wspawnvp
- _spawnvp
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
- _wspawnvp
- _spawnvp
- wspawnvp
dev_langs:
- C++
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
caps.latest.revision: 16
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7ed2815a03df5a189193d547e20c03103325f6d6
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp
Erstellt einen Prozess und führt ihn aus.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
intptr_t _spawnvp(  
   int mode,  
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wspawnvp(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mode`  
 Ausführungsmodus für den aufrufenden Prozess  
  
 `cmdname`  
 Pfad der auszuführenden Datei.  
  
 `argv`  
 Array von Zeigern zu Argumenten. Das `argv`[0]-Argument ist gewöhnlich ein Zeiger auf einen Pfad im Echtzeitmodus oder auf den Programmnamen im geschützten Modus und `argv`[1] bis `argv`[`n`] sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden. Das Argument `argv`[`n` +1] muss ein `NULL` -Zeiger sein, um das Ende der Argumentliste zu markieren.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert eines synchronen `_spawnvp` oder `_wspawnvp` (`_P_WAIT` angegeben für `mode`) ist der Beendigungsstatus des neuen Prozesses. Der Rückgabewert eines asynchronen `_spawnvp` oder `_wspawnvp` (`_P_NOWAIT` oder `_P_NOWAITO` angegeben für `mode`) ist das Prozesshandle. Der Beendigungsstatus ist 0, wenn der Prozess ordnungsgemäß beendet wurde. Sie können den Beendigungsstatus auf einen Wert ungleich 0 einstellen, wenn der gestartete Prozess die `exit` -Routine speziell mit einem Argument ungleich 0 aufruft. Wenn der neue Prozess nicht explizit einen positiven Beendigungsstatus eingestellt hat, weist ein positiver Beendigungsstatus auf eine abnormale Beendigung mit einem Abbruch oder einer Unterbrechung hin. Ein Rückgabewert "-1" gibt einen Fehler (der neue Prozess wird nicht gestartet) an. In diesem Fall wird `errno` auf einen der folgenden Werte festgelegt:  
  
 `E2BIG`  
 Argumentliste umfasst mehr als 1024 Byte.  
  
 `EINVAL`  
 `mode` -Argument ist ungültig.  
  
 `ENOENT`  
 Datei oder Pfad nicht gefunden.  
  
 `ENOEXEC`  
 Die angegebene Datei ist nicht ausführbar oder hat ein ungültiges Format für eine ausführbare Datei.  
  
 `ENOMEM`  
 Es ist nicht genügend Arbeitsspeicher verfügbar, um den neuen Prozess auszuführen.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen erstellt einen neuen Prozess, führt ihn aus, übergibt ein Array von Zeigern auf Befehlszeilenargumente und sucht die auszuführende Datei mithilfe der `PATH` -Umgebungsvariablen.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `cmdname` oder `argv` ein NULL-Zeiger ist oder wenn `argv` auf einen NULL-Zeiger zeigt oder wenn `argv[0]` eine leere Zeichenfolge ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md)ausgeführt werden. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL`ein und geben – 1 zurück. Es wird kein neuer Prozess erzeugt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_spawnvp`|\<stdio.h> oder \<process.h>|  
|`_wspawnvp`|\<stdio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
