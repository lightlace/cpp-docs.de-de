---
title: gets, _getws
ms.date: 11/04/2016
api_name:
- _getws
- gets
api_location:
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getts
- gets
- _getws
helpviewer_keywords:
- getws function
- getts function
- _getws function
- lines, getting
- streams, getting lines
- _getts function
- gets function
- standard input, reading from
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
ms.openlocfilehash: 722d67336e11250f6a5459078dcea173f69bc2af
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944340"
---
# <a name="gets-_getws"></a>gets, _getws

Ruft eine Zeile aus dem `stdin` -Stream ab. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
>  Diese Funktionen sind veraltet. Von Visual Studio 2015 an sind sie nicht in der CRT verfügbar. Dies sicheren Versionen dieser Funktionen, „gets_s“ und „_getws_s“, stehen noch zur Verfügung. Informationen zu diesen alternativen Funktionen finden Sie unter [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).

> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```
char *gets(
   char *buffer
);
wchar_t *_getws(
   wchar_t *buffer
);
template <size_t size>
char *gets(
   char (&buffer)[size]
); // C++ only
template <size_t size>
wchar_t *_getws(
   wchar_t (&buffer)[size]
); // C++ only
```

#### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Eingabezeichenfolge.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg das Argument zurück. Ein **NULL**-Zeiger weist auf einen Fehler oder eine Dateiendebedingung hin. Verwenden Sie [ferror](../c-runtime-library/reference/ferror.md) oder [feof](../c-runtime-library/reference/feof.md) , um festzulegen, was aufgetreten ist. Wenn `buffer` **NULL** ist, rufen diese Funktionen, wie in [Parametervalidierung](../c-runtime-library/parameter-validation.md) beschrieben, den Handler für ungültige Parameter auf. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen **NULL** zurück und setzen „errno“ auf `EINVAL`.

## <a name="remarks"></a>Anmerkungen

Die `gets`-Funktion liest eine Zeile aus dem Standardeingabestream `stdin` und speichert sie in `buffer`. Die Zeile enthält alle Zeichen einschließlich des ersten Zeilenumbruchzeichens ('\n'). `gets` ersetzt dann das Zeilenumbruchzeichen durch ein NULL-Zeichen ('\0'), ehe die Zeile zurückgegeben wird. Im Gegensatz dazu behält die `fgets` -Funktion das Zeilenumbruchzeichen bei. `_getws` ist eine Breitzeichenversion von `gets`. Das Argument und der Rückgabewert sind Breitzeichen-Zeichenfolgen.

> [!IMPORTANT]
>  Da es keine Möglichkeit gibt, die Anzahl von Zeichen einzuschränken, die von "gets" gelesen werden, kann eine nicht vertrauenswürdige Eingabe zu Pufferüberläufen führen. Verwenden Sie stattdessen `fgets` .

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_getts`|`gets`|`gets`|`_getws`|

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`gets`|\<stdio.h>|
|`_getws`|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```
// crt_gets.c
// compile with: /WX /W3

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C4996
   // Danger: No way to limit input to 20 chars.
   // Consider using gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

Beachten Sie, dass Eingaben, die länger als 20 Zeichen sind, zu einem Überlauf des Zeilenpuffers führen und das Programm vermutlich zum Absturz bringen.

```Output

Hello there!The line entered was: Hello there!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)<br/>
[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)<br/>
[puts, _putws](../c-runtime-library/reference/puts-putws.md)
