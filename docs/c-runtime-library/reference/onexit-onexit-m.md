---
title: _onexit, _onexit_m | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: caa4c732449864c4803a25f3bb123c43495f5fc1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m
Registriert eine Routine, die zum Zeitpunkt der Beendigung aufgerufen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `function`  
 Zeiger an eine bei Beendigung aufzurufende Funktion.  
  
## <a name="return-value"></a>Rückgabewert  
 `_onexit` gibt bei Erfolg einen Zeiger an die Funktion zurück oder `NULL`, wenn kein Speicherplatz zum Speichern des Funktionszeigers vorhanden ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Programm normal beendet wird, wird die Adresse einer aufzurufenden Funktion (`function`) der `_onexit`-Funktion übergeben. Aufeinanderfolgende Aufrufe von `_onexit` führen zur Erstellung eines Registers von Funktion, die in LIFO-Reihenfolge (last-in, first-out) ausgeführt werden. Die an `_onexit` übergebenen Funktionen können keine Parameter verwenden.  
  
 Wird `_onexit` innerhalb einer DLL aufgerufen, werden Routinen, die in einer `_onexit` registriert sind, nach dem Entladen des `DllMain` mit DLL_PROZESS_DETACH auf einer DLL-Datei ausgeführt.  
  
 `_onexit` ist eine Microsoft-Erweiterung. Verwenden Sie für ANSI-Portabilität [Atexit](../../c-runtime-library/reference/atexit.md). Die `_onexit_m`-Version der Funktion besteht zur Verwendung des gemischten Modus.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__dllonexit](../../c-runtime-library/dllonexit.md)