---
title: _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _cprintf_p_l
- _cwprintf_p_l
- _cwprintf_p
- _cprintf_p
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
- cprintf_p
- cwprintf_p
- tcprintf_p
- _cwprintf_p_l
- _cprintf_p
- csprintf_p_l
- _cprintf_p_l
- _cwprintf_p
- _tcprintf_p
- cprintf_p_l
dev_langs:
- C++
helpviewer_keywords:
- _cwprintf_p_l function
- cwprintf_p function
- tcprintf_p_l function
- cprintf_p_l function
- _tcprintf_p function
- _tcprintf_p_l function
- _cprintf_p function
- _cprintf_p_l function
- cwprintf_p_l function
- _cwprintf_p function
- tcprintf_p function
- cprintf_p function
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99994c73b477fd41bd080117fe1dc2ba6b388ded
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="cprintfp-cprintfpl-cwprintfp-cwprintfpl"></a>_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l

Formatiert Daten und gibt diese über die Konsole aus und unterstützt positionelle Parameter in der Formatzeichenfolge.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _cprintf_p(
   const char * format [,
   argument] ...
);
int _cprintf_p_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_p(
   const wchar * format [,
   argument] ...
);
int _cwprintf_p_l(
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

Die Anzahl gedruckter Zeichen oder ein negativer Wert im Falle eines Fehlers.

## <a name="remarks"></a>Hinweise

Diese Funktionen formatieren und drucken Sie eine Reihe von Zeichen und Werte direkt in der Konsole mit der **_putch** und **_putwch** Funktionen für die Zeichenausgabe. Jede *Argument* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Das Format hat dieselbe form und Funktion wie die *Format* -Parameter für die [Printf_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) Funktion. Der Unterschied zwischen **_cprintf_p** und **Cprintf_s** handelt, **_cprintf_p** positionelle Parameter unterstützt, wodurch ermöglicht das Angeben der Reihenfolge, in denen die Argumente sind, in der Formatzeichenfolge verwendet. Weitere Informationen finden Sie unter [printf-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).

Im Gegensatz zu den **Fprintf_p**, **Printf_p**, und **Sprintf_p** -Funktionen übersetzen weder **_cprintf_p** noch **_cwprintf_p** übersetzt Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub (CR-LF) Kombinationen bei der Ausgabe. Ein wichtiger Unterschied ist, die **_cwprintf_p** zeigt bei der Verwendung in Windows NT Unicode-Zeichen. Im Gegensatz zu **_cprintf_p**, **_cwprintf_p** verwendet die aktuellen Einstellungen des konsolengebietsschemas.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter anstelle des aktuellen Gebietsschemas übergeben.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

Ebenso wie **_cprintf_s** und **_cwprintf_s**, überprüfen sie den Eingabezeiger und die Formatzeichenfolge. Wenn *Format* oder *Argument* sind **NULL**, oder das Format ungültige Formatierungszeichen enthält, rufen diese Funktionen den Handler für ungültige Parameter als in der beschriebenen [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen – 1 zurück und legen Sie **Errno** auf **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_p**|**_cprintf_p**|**_cprintf_p**|**_cwprintf_p**|
|**_tcprintf_p_l**|**_cprintf_p_l**|**_cprintf_p_l**|**_cwprintf_p_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_cprintf_p**, **_cprintf_p_l**|\<conio.h>|
|**_cwprintf_p**, **_cwprintf_p_l**|\<conio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_cprintf_p.c
// This program displays some variables to the console
// using the _cprintf_p function.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate
    // \n as standard output does. Use \r\n instead.
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",
                h, i, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>Siehe auch

[Konsole und Port-E/A](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
