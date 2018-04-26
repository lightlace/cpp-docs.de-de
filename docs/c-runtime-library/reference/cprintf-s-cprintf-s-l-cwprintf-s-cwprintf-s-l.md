---
title: _cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _cwprintf_s_l
- _cprintf_s_l
- _cprintf_s
- _cwprintf_s
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
- _cwprintf_s_l
- _cprintf_s
- cwprintf_s
- _cprintf_s_l
- cwprintf_s_l
- cprintf_s_l
- _tcprintf_s
- cprintf_s
- _cwprintf_s
- tcprintf_s
dev_langs:
- C++
helpviewer_keywords:
- tcprintf_s_l function
- _cprintf_s_l function
- _cwprintf_s_l function
- tcprintf_s function
- _tcprintf_s_l function
- _cwprintf_s function
- cwprintf_s function
- _cprintf_s function
- cprintf_s function
- _tcprintf_s function
- cprintf_s_l function
- cwprintf_s_l function
ms.assetid: c28504fe-0d20-4f06-8f97-ee33225922ad
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e87cf1c80dbea9f16060dc0ad928b1edfb0e4b52
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="cprintfs-cprintfsl-cwprintfs-cwprintfsl"></a>_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l

Formatiert und druckt in die Konsole. Diese Versionen von [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md) enthalten Sicherheitserweiterungen unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _cprintf_s(
   const char * format [,
   argument] ...
);
int _cprintf_s_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_s(
   const wchar * format [,
   argument] ...
);
int _cwprintf_s_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parameter

*format*<br/>
Formatsteuerzeichenfolge.

*Argument*<br/>
Optionale Parameter.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der zu gedruckten Zeichen.

## <a name="remarks"></a>Hinweise

Diese Funktionen formatieren und drucken Sie eine Reihe von Zeichen und Werte direkt in der Konsole mit der **_putch** Funktion (**_putwch** für **_cwprintf_s**) in die Ausgabe Zeichen. Jede *Argument* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Das Format hat dieselbe form und Funktion wie die *Format* -Parameter für die [Printf_s](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) Funktion. Im Gegensatz zu den **Fprintf_s**, **Printf_s**, und **Sprintf_s** -Funktionen übersetzen weder **_cprintf_s** noch **_cwprintf_s** übersetzt Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub (CR-LF) Kombinationen bei der Ausgabe.

Ein wichtiger Unterschied ist, die **_cwprintf_s** zeigt bei der Verwendung in Windows NT Unicode-Zeichen. Im Gegensatz zu **_cprintf_s**, **_cwprintf_s** verwendet das aktuelle Gebietsschema für die Konsole

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter anstelle des aktuellen Gebietsschemas übergeben.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

Wie Sie die nicht sicheren Versionen (finden Sie unter [_cprintf _cprintf_l, _cwprintf _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)), diese Funktionen überprüfen ihre Parameter und den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md), wenn *Format* ist ein null-Zeiger. Diese Funktionen unterscheiden sich von den nicht sicheren Versionen darin, dass auch die Formatzeichenfolge selbst überprüft wird. Gibt es unbekannte oder ungültige Formatbezeichner, rufen diese Funktionen den Handler für ungültige Parameter auf. In allen Fällen, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen – 1 zurück und legen Sie **Errno** auf **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_s**|**_cprintf_s**|**_cprintf_s**|**_cwprintf_s**|
|**_tcprintf_s_l**|**_cprintf_s_l**|**_cprintf_s_l**|**_cwprintf_s_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_cprintf_s**, **_cprintf_s_l**|\<conio.h>|
|**_cwprintf_s**, **_cwprintf_s_l**|\<conio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_cprintf_s.c
// compile with: /c
// This program displays some variables to the console.

#include <conio.h>

int main( void )
{
   int      i = -16, h = 29;
   unsigned u = 62511;
   char     c = 'A';
   char     s[] = "Test";

   /* Note that console output does not translate \n as
    * standard output does. Use \r\n instead.
    */
   _cprintf_s( "%d  %.4x  %u  %c %s\r\n", i, h, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>Siehe auch

[Konsole und Port-E/A](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)<br/>
[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
