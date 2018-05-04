---
title: _setmbcp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- setmbcp function
- _setmbcp function
- multibyte code pages
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91993171def417adfc389420d1376e5a71f8cda0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

*Codepage*<br/>
Neue Codepageeinstellung für gebietsschemaunabhängige Multibyte-Routinen.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn die Codepage erfolgreich festgelegt wurde. Wenn ein ungültiger Codepagewert für angegeben wird *Codepage*,-1 und die Codepage-Einstellung wird unverändert zurückgegeben. Legt **Errno** auf **EINVAL** Wenn ein speicherbelegungsfehler auftritt.

## <a name="remarks"></a>Hinweise

Die **_setmbcp** -Funktion gibt eine multibyte-Codepage an. Standardmäßig legt das Laufzeitsystem automatisch die Multibyte-Codepage auf die Systemstandard-ANSI-Codepage fest. Die Multibyte-Codepageeinstellung wirkt sich auf alle Multibyteroutinen auf, die nicht vom Gebietsschema abhängig sind. Allerdings ist es möglich, weisen Sie **_setmbcp** verwendet die Codepage für das aktuelle Gebietsschema definiert (siehe die folgende Liste von Manifestkonstanten, und die zugehörigen Verhalten Ergebnisse). Eine Liste der Multibyteroutinen, die von der Gebietsschema-Codepage und nicht von der Multibyte-Codepage abhängig sind, finden Sie unter [Interpretation von Multybite-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).

Die Multibyte-Codepage hat auch Auswirkungen auf die Multibyteverarbeitung durch die folgenden Routinen der Laufzeitbibliothek:

||||
|-|-|-|
|[_exec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)|[_mktemp](mktemp-wmktemp.md)|[_stat](stat-functions.md)|
|[_fullpath](fullpath-wfullpath.md)|[_spawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[_makepath](makepath-wmakepath.md)|[_splitpath](splitpath-wsplitpath.md)|[tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|

Darüber hinaus alle Laufzeitbibliothek-Routinen, die Multibyte-Zeichenfolgen empfangen *Argv* oder *Envp* Programmieren Argumente als Parameter (z. B. die **_exec** und **_spawn** Familien) verarbeiten diese Zeichenfolgen gemäß der multibyte-Codepage. Daher sind diese Routinen ebenfalls betroffen durch einen Aufruf von **_setmbcp** multibyte-Codepage ändert.

Die *Codepage* Argument kann eines der folgenden Werte festgelegt werden:

- **_MB_CP_ANSI** verwenden ANSI-Codepage, die vom Betriebssystem beim Programmstart abgerufen.

- **_MB_CP_LOCALE** verwenden, die das aktuelle Gebietsschema-Codepage, von einem vorherigen Aufruf von abgerufen [Setlocale](setlocale-wsetlocale.md).

- **_MB_CP_OEM** verwenden OEM-Codepage, die vom Betriebssystem beim Programmstart abgerufen.

- **_MB_CP_SBCS** Einzelbyte-Codepage verwenden. Wenn die Codepage festgelegt wird, um **_MB_CP_SBCS**, eine Routine, wie z. B. [_ismbblead](ismbblead-ismbblead-l.md) immer "false" zurückgegeben.

- Jeder beliebige andere gültige Codepage-Wert unabhängig davon, ob der Wert eine ANSI-, OEM- oder einem anderen Betriebssystem unterstützte Codepage ist (außer UTF-7 und UTF-8, die nicht unterstützt werden).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_setmbcp**|\<mbctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_getmbcp](getmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
