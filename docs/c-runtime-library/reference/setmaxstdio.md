---
title: _setmaxstdio | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5317437202cef423759ac850aab2360892521746
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="setmaxstdio"></a>_setmaxstdio
Legt die maximale Anzahl von Dateien fest, die auf der `stdio`-Ebene gleichzeitig geöffnet sein können.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `newmax`  
 Maximale Anzahl von Dateien, die auf der `stdio`-Ebene gleichzeitig geöffnet sein können.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `newmax` Wenn erfolgreich, andernfalls -1.  
  
 Wenn `newmax` kleiner als `_IOB_ENTRIES` oder größer als die maximale Anzahl von Handles ist, die im Betriebssystem verfügbar sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die Ausführung weiterhin zugelassen wird, gibt diese Funktion -1 zurück und legt `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_setmaxstdio`-Funktion ändert den Maximalwert für die Anzahl von Dateien, die gleichzeitig auf `stdio`-Ebene geöffnet sein können.  
  
 C-Laufzeit-E/A unterstützt nun eine größere Anzahl von geöffneten Dateien auf Win32-Plattformen als in früheren Versionen. Bis zu 2.048 Dateien können gleichzeitig auf [Lowio-Ebene](../../c-runtime-library/low-level-i-o.md) geöffnet sein (d.h. geöffnet und durch die `_open`-, `_read`-, `_write`- usw. E/A-Funktionsfamilie zugänglich). Bis zu 512 Dateien können gleichzeitig auf [Lowio-Ebene](../../c-runtime-library/stream-i-o.md) geöffnet sein (d.h. geöffnet und durch die `fopen`-, `fgetc`-, `fputc`-E/A-Funktionsfamilie usw. zugänglich). Die Obergrenze von 512 geöffnete Dateien auf `stdio`-Ebene kann mithilfe der `_setmaxstdio`-Funktion auf maximal 2.048 erhöht werden.  
  
 Da Funktionen der `stdio`-Ebene, wie z.B. `fopen`, auf den `lowio`-Funktionen aufsetzen, ist das Maximum von 2.048 eine feste Obergrenze für die Anzahl von gleichzeitig geöffneten Dateien, auf die über die C-Laufzeitbibliothek zugegriffen wird.  
  
> [!NOTE]
>  Die Obergrenze überschreitet möglicherweise die von einer bestimmten Win32-Plattform und -Konfiguration unterstützte Grenze.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Unter [_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) finden Sie ein Beispiel der Verwendung von `_setmaxstdio`.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)