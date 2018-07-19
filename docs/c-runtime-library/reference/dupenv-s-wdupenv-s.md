---
title: _dupenv_s, _wdupenv_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a918b866b0b43fb0e6b31e2deb5d9861dabe9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402113"
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

Diese Funktionen überprüfen ihre Parameter; Wenn *Puffer* oder *Varname* ist **NULL**, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen die Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

Wenn diese Funktionen nicht genügend Arbeitsspeicher zuordnen können, legen sie *Puffer* auf **NULL** und *NumberOfElements* auf 0, und der Rückgabewert **ENOMEM**.

## <a name="remarks"></a>Hinweise

Die **_dupenv_s** -Funktion sucht die Liste von Umgebungsvariablen für *Varname*. Wenn die Variable gefunden wird, **_dupenv_s** einen Puffer und der Wert der Variablen in den Puffer kopiert. Adresse und die Länge des Puffers werden in zurückgegeben *Puffer* und *NumberOfElements*. Durch das Zuweisen des Puffers selbst **_dupenv_s** bietet eine besser geeignete Alternative zu [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Das aufrufende Programm ist dafür zuständig, den Arbeitsspeicher durch Aufruf von [free](free.md) zu leeren.

Wenn die Variable nicht, klicken Sie dann gefunden wird *Puffer* festgelegt ist, um **NULL**, *NumberOfElements* auf 0 (null) festgelegt ist und der Rückgabewert ist 0, da diese Situation ist kein Fehler Bedingung.

Wenn Sie nicht die Größe des Puffers interessiert sind können Sie übergeben **NULL** für *NumberOfElements*.

**_dupenv_s** ist nicht in der Groß-/Kleinschreibung beachtet, in der Windows-Betriebssystem. **_dupenv_s** verwendet die Kopie der Umgebung verweist die globale Variable **_environ** auf die Umgebung zuzugreifen. Siehe die Hinweise in [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) eine Erläuterung der **_environ**.

Der Wert in *Puffer* ist eine Kopie des Werts für die Umgebungsvariable; diese zu ändern, hat keine Auswirkung auf die Umgebung. Verwenden Sie die Funktion [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md), um den Wert einer Umgebungsvariablen zu ändern.

**_wdupenv_s** ist eine Breitzeichen-Version von **_dupenv_s**; die Argumente der **_wdupenv_s** sind Zeichenfolgen mit Breitzeichen. Die **_wenviron** (globale Variable) ist eine Breitzeichen-Version von **_environ**. Siehe die Hinweise in [Getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) für Weitere Informationen über die **_wenviron**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
