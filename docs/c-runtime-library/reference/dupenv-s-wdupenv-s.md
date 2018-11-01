---
title: _dupenv_s, _wdupenv_s
ms.date: 11/04/2016
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: bc8af3282b57c9fa411aac97f5fa4d414bc3305b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646498"
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s

Ruft einen Wert aus der aktuellen Umgebung ab.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Puffer zum Speichern des Variablenwerts.

*numberOfElements*<br/>
Größe des *Puffer*.

*Variablenname*<br/>
Umgebungsvariablenname.

## <a name="return-value"></a>Rückgabewert

Null bei Erfolg, ein Fehlercode, wenn ein Fehler auftritt.

Diese Funktionen überprüfen ihre Parameter; Wenn *Puffer* oder *Varname* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzen die Funktionen **Errno** zu **EINVAL** und zurückgeben **EINVAL**.

Wenn diese Funktionen können nicht genügend Arbeitsspeicher zuordnen, die sie festgelegt *Puffer* zu **NULL** und *NumberOfElements* 0, und Rückgabe **ENOMEM**.

## <a name="remarks"></a>Hinweise

Die **_dupenv_s** -Funktion sucht die Liste von Umgebungsvariablen für *Varname*. Wenn die Variable gefunden wird, **_dupenv_s** weist einen Puffer und kopiert den Wert der Variablen in den Puffer. Adresse und die Länge des Puffers in zurückgegeben werden *Puffer* und *NumberOfElements*. Durch die selbstzuweisung des Puffers, **_dupenv_s** bietet eine zweckmäßigere Alternative zu [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Das aufrufende Programm ist dafür zuständig, den Arbeitsspeicher durch Aufruf von [free](free.md) zu leeren.

Wenn die Variable nicht, klicken Sie dann gefunden wird *Puffer* nastaven NA hodnotu **NULL**, *NumberOfElements* auf 0 (null) festgelegt ist und der Rückgabewert ist 0, da diese Situation kein Fehler betrachtet wird Bedingung.

Wenn Sie nicht die Größe des Puffers interessiert sind können Sie übergeben **NULL** für *NumberOfElements*.

**_dupenv_s** ist nicht in der Groß-/Kleinschreibung beachtet, im Windows-Betriebssystem. **_dupenv_s** verwendet die Kopie der Umgebung auf die globale Variable zeigt **_environ** auf die Umgebung zuzugreifen. Finden Sie unter den Hinweisen in [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) eine Erläuterung der **_environ**.

Der Wert in *Puffer* ist eine Kopie der der Wert der Umgebungsvariablen; Änderung hat keine Auswirkungen auf die Umgebung. Verwenden Sie die Funktion [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md), um den Wert einer Umgebungsvariablen zu ändern.

**_wdupenv_s** ist eine Breitzeichen-Version von **_dupenv_s**; die Argumente des **_wdupenv_s** sind Breitzeichen Zeichenfolgen. Die **_wenviron** globale Variable ist eine Breitzeichen-Version von **_environ**. Finden Sie unter den Hinweisen in [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) Weitere Informationen zu **_wenviron**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
