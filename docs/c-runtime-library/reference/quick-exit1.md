---
title: quick_exit1 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30c8ae3290ac4b15247b88b0b2201634e42b560b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="quickexit"></a>quick_exit
Bewirkt eine normale Programmbeendigung.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Status  
 Der an die Hostumgebung zurückzugebende Statuscode.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `quick_exit` -Funktion kann nichts an den Aufrufer zurückgeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `quick_exit` -Funktion bewirkt eine normale Programmbeendigung. Sie ruft keine von `atexit`oder `_onexit` registrierten Funktionen oder durch die `signal` -Funktion registrierten Signalhandler auf. Das Verhalten ist undefiniert, wenn `quick_exit` mehrfach aufgerufen wird oder wenn die Funktion `exit` ebenfalls aufgerufen wird.  
  
 Die Funktion `quick_exit` ruft die von `at_quick_exit`registrierten Funktionen in LIFO-Reihenfolge (Last-In, First-Out) auf, abgesehen von den beim Registrieren der Funktion bereits aufgerufenen Funktionen.  Da Verhalten ist undefiniert, wenn ein [longjmp](../../c-runtime-library/reference/longjmp.md) -Aufruf während des Aufrufs einer registrierten Funktion erfolgt, die den Aufruf der Funktion beenden würde.  
  
 Nachdem die registrierten Funktionen aufgerufen wurden, ruft `quick_exit` `_Exit` auf und verwendet dazu den `status` -Wert, um die Steuerung an die Hostumgebung zurückzugeben.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`quick_exit`|\<process.h> oder\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)