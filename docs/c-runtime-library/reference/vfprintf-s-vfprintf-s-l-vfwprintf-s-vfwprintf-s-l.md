---
title: vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vfwprintf_s
- _vfprintf_s_l
- vfprintf_s
- _vfwprintf_s_l
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
- _vftprintf_s
- vfwprintf_s
- vfprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vfprintf_s_l function
- vfwprintf_s_l function
- vfwprintf_s function
- _vfprintf_s_l function
- _vfwprintf_s_l function
- vftprintf_s_l function
- vfprintf_s function
- _vftprintf_s_l function
- formatted text [C++]
- _vftprintf_s function
ms.assetid: eab6f563-46e2-4806-963f-2b23f339ecdc
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ad82a85b00f04620bf52bdf478c5293905b75aca
ms.lasthandoff: 02/24/2017

---
# <a name="vfprintfs-vfprintfsl-vfwprintfs-vfwprintfsl"></a>vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l
Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Dies sind Versionen von [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) mit Sicherheitserweiterungen, die unter [Security Features in the CRT (Sicherheitserweiterungen in der CRT)](../../c-runtime-library/security-features-in-the-crt.md) beschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
int vfprintf_s(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_s_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vfwprintf_s(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_s_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Rückgabewert  
 `vfprintf_s` und `vfwprintf_s` geben die Anzahl der geschriebenen Zeichen ohne das abschließende Nullzeichen zurück oder einen negativen Wert, wenn ein Ausgabefehler auftritt. Wenn `stream` oder `format` ein NULL-Zeiger ist oder wenn Formatzeichenfolge ungültige Formatierungszeichen enthält, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen –&1; zurück und legen `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt anschließend die vorhandenen Daten in `stream`.  
  
 Diese Funktionen unterscheiden sich von nicht sicheren Versionen insofern, als die sicheren Versionen überprüfen, ob die `format`-Zeichenfolge gültige Formatierungszeichen enthält.  
  
 `vfwprintf_s` ist die Breitzeichenversion von `vfprintf_s`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. `vfprintf_s` unterstützt derzeit die Ausgabe in einen UNICODE-Stream nicht.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf_s`|`vfprintf_s`|`vfprintf_s`|`vfwprintf_s`|  
|`_vftprintf_s_l`|`_vfprintf_s_l`|`_vfprintf_s_l`|`_vfwprintf_s_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`vfprintf_s`, _`vfprintf_s_l`|\<stdio.h> und \<stdarg.h>|\<varargs.h>*|  
|`vfwprintf_s`, _`vfwprintf_s_l`|\<stdio.h> oder \<wchar.h> und \<stdarg.h>|\<varargs.h>*|  
  
 \* Benötigt für die Kompatibilität mit UNIX V.  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Stream I/O (Stream-E/A)](../../c-runtime-library/stream-i-o.md)   
 [vprintf Functions (vprintf-Funktionen)](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
