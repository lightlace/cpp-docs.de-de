---
title: _setmbcp
ms.date: 11/04/2016
apiname:
- _setmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _setmbcp
- setmbcp
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
ms.openlocfilehash: c1f4967baa5fda68a7df33bcd08935dca23fab16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356458"
---
# <a name="setmbcp"></a>_setmbcp

Legt eine neue Multibyte-Codepage fest.

## <a name="syntax"></a>Syntax

```C
int _setmbcp(
   int codepage
);
```

### <a name="parameters"></a>Parameter

*codepage*<br/>
Neue Codepageeinstellung für gebietsschemaunabhängige Multibyte-Routinen.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Codepage erfolgreich festgelegt wurde. Wenn ein ungültige Codepagewert für angegeben wird *Codepage*, gibt – 1 und die codepageeinstellung wird nicht geändert. Legt **Errno** zu **EINVAL** im Falle einer speicherbelegungsfehlers.

## <a name="remarks"></a>Hinweise

Die **_setmbcp** -Funktion gibt eine neue multibyte-Codepage an. Standardmäßig legt das Laufzeitsystem automatisch die Multibyte-Codepage auf die Systemstandard-ANSI-Codepage fest. Die Multibyte-Codepageeinstellung wirkt sich auf alle Multibyteroutinen auf, die nicht vom Gebietsschema abhängig sind. Es ist jedoch möglich, weisen Sie **_setmbcp** für das aktuelle Gebietsschema definierte Codepage zu verwenden (finden Sie unter der folgenden Liste der Manifestkonstanten und zugeordnete verhaltensergebnisse). Eine Liste der Multibyteroutinen, die von der Gebietsschema-Codepage und nicht von der Multibyte-Codepage abhängig sind, finden Sie unter [Interpretation von Multybite-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Die Multibyte-Codepage hat auch Auswirkungen auf die Multibyteverarbeitung durch die folgenden Routinen der Laufzeitbibliothek:

||||
|-|-|-|
|[_exec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Darüber hinaus alle-Laufzeitbibliotheksroutinen, die Multibyte-Zeichensätze erhalten *Argv* oder *Envp* Programmargumente als Parameter (z. B. die **_exec** und **_spawn** Familien) verarbeiten diese Zeichenfolgen gemäß der Mehrbyte-Codepage. Diese Routinen sind daher ebenfalls betroffen, durch einen Aufruf von **_setmbcp** , die multibyte-Codepage ändert.

Die *Codepage* Argument kann auf eine der folgenden Werte festgelegt werden:

- **_MB_CP_ANSI** mit ANSI-Codepage, die vom Betriebssystem beim Programmstart abgerufene.

- **_MB_CP_LOCALE** verwenden das aktuelle Gebietsschema-Codepage aus einem vorherigen Aufruf von [Setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** verwenden OEM-Codepage, die vom Betriebssystem beim Programmstart abgerufene.

- **_MB_CP_SBCS** Einzelbyte-Codepage verwenden. Wenn die Codepage auf festgelegt ist **_MB_CP_SBCS**, eine Routine, wie z. B. [_ismbblead](ismbblead-ismbblead-l.md) gibt immer false zurück.

- Jeder beliebige andere gültige Codepage-Wert unabhängig davon, ob der Wert eine ANSI-, OEM- oder einem anderen Betriebssystem unterstützte Codepage ist (außer UTF-7 und UTF-8, die nicht unterstützt werden).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
