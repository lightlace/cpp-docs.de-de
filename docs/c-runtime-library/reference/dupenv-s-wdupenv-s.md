---
title: _dupenv_s, _wdupenv_s
ms.date: 11/04/2016
api_name:
- _dupenv_s
- _wdupenv_s
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: f66828e0941c2324d75797cbb1fa77bdfa184205
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942021"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

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
Größe des *Puffers*.

*varname*<br/>
Umgebungsvariablenname.

## <a name="return-value"></a>Rückgabewert

Null bei Erfolg, ein Fehlercode, wenn ein Fehler auftritt.

Diese Funktionen überprüfen Ihre Parameter. Wenn *buffer* oder *varname* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legen die Funktionen " **errno** " auf " **EINVAL** " fest und geben " **EINVAL**" zurück.

Wenn diese Funktionen nicht genügend Arbeitsspeicher zuordnen können, legen Sie den *Puffer* auf **null** und die *Anzahl* der Werte auf 0 fest und geben **ENOMEM**zurück.

## <a name="remarks"></a>Hinweise

Die **_dupenv_s** -Funktion durchsucht die Liste der Umgebungsvariablen nach *varname*. Wenn die Variable gefunden wird, ordnet **_dupenv_s** einen Puffer zu und kopiert den Wert der Variablen in den Puffer. Die Adresse und die Länge des Puffers werden in *buffer* und *nummerioements*zurückgegeben. Wenn Sie den Puffer selbst zuweisen, bietet **_dupenv_s** eine etwas bequemere Alternative zu [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Das aufrufende Programm ist dafür zuständig, den Arbeitsspeicher durch Aufruf von [free](free.md) zu leeren.

Wenn die Variable nicht gefunden wird, wird *buffer* auf **null**festgelegt, der Wert für " *" ist auf* "0" festgelegt, und der Rückgabewert ist 0, da diese Situation nicht als Fehlerbedingung angesehen wird.

Wenn Sie nicht an der Größe des Puffers interessiert sind, können Sie **null** für " *numofelements*" übergeben.

bei **_dupenv_s** wird im Windows-Betriebssystem die Groß-/Kleinschreibung nicht beachtet **_dupenv_s** verwendet die Kopie der Umgebung, auf die durch die globale Variable **_environ** verwiesen wird, um auf die Umgebung zuzugreifen. Eine Erläuterung zu **_environ**finden Sie in den Hinweisen unter [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) .

Der Wert in *buffer* ist eine Kopie des Werts der Umgebungsvariablen. eine Änderung der Umgebung hat keine Auswirkungen auf die Umgebung. Verwenden Sie die Funktion [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md), um den Wert einer Umgebungsvariablen zu ändern.

**_wdupenv_s** ist eine breit Zeichen Version von **_dupenv_s**. die Argumente von **_wdupenv_s** sind Zeichen folgen mit breit Zeichen. Die globale **_wenviron** -Variable ist eine breit Zeichen Version von **_environ**. Weitere Informationen zu **_wenviron**finden Sie in den Hinweisen unter [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) .

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
