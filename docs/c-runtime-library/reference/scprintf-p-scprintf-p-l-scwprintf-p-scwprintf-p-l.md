---
title: _scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _scwprintf_p
- _scprintf_p_l
- _scwprintf_p_l
- _scprintf_p
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
- _scwprintf_p_l
- _sctprintf_p
- scprintf_p_l
- scprintf_p
- _sctprintf_p_l
- scwprintf_p
- _scprintf_p_l
- scwprintf_p_l
- _scprintf_p
- _scwprintf_p
dev_langs: C++
helpviewer_keywords:
- sctprintf_p_l function
- _scwprintf_p_l function
- scprintf_p_l function
- _scprintf_p function
- _scprintf_p_l function
- scprintf_p function
- sctprintf_p function
- _scwprintf_p function
- _sctprintf_p function
- scwprintf_p function
- scwprintf_p_l function
- _sctprintf_p_l function
ms.assetid: 8390d1e1-2826-47a4-851f-6635a88087cc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84e0cae612e1ee27b841089176ce1e2dfa368d29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scprintfp-scprintfpl-scwprintfp-scwprintfpl"></a>_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l
Gibt die Anzahl der Zeichen in der formatierten Zeichenfolge zurück, bietet der Möglichkeit, die Reihenfolge anzugeben, in der Parameter in der Formatzeichenfolge verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _scprintf_p(  
   const char *format [,  
   argument] ...   
);  
int _scprintf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _scwprintf_p (  
   const wchar_t *format [,  
   argument] ...   
);  
int _scwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Zeichen zurück, die erzeugt wird, wenn die Zeichenfolge gedruckt oder mithilfe der angegebenen Formatierungscodes an eine Datei oder einen Puffer gesendet wird. Der Rückgabewert umfasst nicht das abschließende NULL-Zeichen. `_scwprintf_p` führt die gleiche Funktion für Breitzeichen aus.  
  
 Der Unterschied zwischen `_scprintf_p` und `_scprintf` ist, dass `_scprintf_p` Positionsparameter unterstützt, wodurch festgelegt werden kann, in welcher Reihenfolge die Argumente in der Formatzeichenfolge verwendet werden. Weitere Informationen finden Sie unter [printf-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Wenn `format` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jedes `argument` (falls vorhanden) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert. Das Format besteht aus normalen Zeichen und hat die gleiche Form und Funktion wie das `format`-Argument für [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Die Versionen dieser Funktionen mit dem `_l` -Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_sctprintf_p`|`_scprintf_p`|`_scprintf_p`|`_scwprintf_p`|  
|`_sctprintf_p_l`|`_scprintf_p_l`|`_scprintf_p_l`|`_scwprintf_p_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_scprintf_p`, `_scprintf_p_l`|\<stdio.h>|  
|`_scwprintf_p`, `_scwprintf_p_l`|\<stdio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_scprintf, _scprintf_l, _scwprintf, _scwprintf_l](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md)   
 [_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)