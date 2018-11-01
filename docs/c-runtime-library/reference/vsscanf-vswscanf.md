---
title: vsscanf, vswscanf
ms.date: 11/04/2016
apiname:
- vsscanf
- vswscanf
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
- _vstscanf
- vsscanf
- vswscanf
helpviewer_keywords:
- vswscanf function
- vsscanf function
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
ms.openlocfilehash: 5bbe80cd2463c5c5b9b4ea55b8d6574675e42054
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478582"
---
# <a name="vsscanf-vswscanf"></a>vsscanf, vswscanf

Liest formatierte Daten aus einer Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md).

## <a name="syntax"></a>Syntax

```C
int vsscanf(
   const char *buffer,
   const char *format,
   va_list arglist
);
int vswscanf(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Gespeicherte Daten

*format*<br/>
Formatsteuerzeichenfolge. Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*arglist*<br/>
Variablenargumentenliste.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist **EOF** für einen Fehler oder am Ende der Zeichenfolge vor der ersten Konvertierung erreicht wird.

Wenn *Puffer* oder *Format* ist eine **NULL** -Zeiger ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Vsscanf** -Funktion liest Daten aus *Puffer* in die Speicherorte, die von jedem Argument im erhalten die *Arglist* Argumentliste. Jedes Argument in der Liste muss ein Zeiger auf eine Variable, deren Typ, der einem Typspezifizierer in entspricht *Format*. Die *Format* -Argument steuert die Interpretation der Eingabefelder und hat die gleiche form und Funktion wie der *Format* Argument für die **Scanf** Funktion. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

> [!IMPORTANT]
> Bei Verwendung von **Vsscanf** um eine Zeichenfolge zu lesen, geben Sie immer eine Breite für die **%s** Format (z. B. **"% 32 Sekunden"** anstelle von **"%s"**); falsch formatierte Eingabe kann, andernfalls einen Pufferüberlauf verursachen.

**Vswscanf** ist eine Breitzeichen-Version von **Vsscanf**; die Argumente für **Vswscanf** sind Breitzeichen Zeichenfolgen. **Vsscanf** verarbeitet keine multibyte-Hexadezimalzeichen. **Vswscanf** verarbeitet keine Unicode-voller Breite Hexadezimal- oder im "Kompatibilität der Zone" Zeichen. Andernfalls **Vswscanf** und **Vsscanf** Verhalten sich identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf**|**vsscanf**|**vsscanf**|**vswscanf**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**vsscanf**|\<stdio.h>|
|**vswscanf**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vsscanf.c
// compile with: /W3
// This program uses vsscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>

int call_vsscanf(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf(tokenstring, "%80s", s);
    call_vsscanf(tokenstring, "%c", &c);
    call_vsscanf(tokenstring, "%d", &i);
    call_vsscanf(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md)<br/>
