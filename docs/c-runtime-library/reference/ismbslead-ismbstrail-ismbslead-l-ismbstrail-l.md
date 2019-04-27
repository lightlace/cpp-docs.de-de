---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
ms.date: 11/04/2016
apiname:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
ms.openlocfilehash: 5b4d3f371f4be640cc22a1bdc3d920acf88e2585
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287356"
---
# <a name="ismbslead-ismbstrail-ismbsleadl-ismbstraill"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

Führt kontextbezogene Tests für führende und nachfolgende Bytes mit Multibyte-Zechenfolgen aus und bestimmt, ob ein angegebener Teilzeichenfolgenzeiger auf ein führendes Byte oder ein nachfolgendes Byte zeigt.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zeiger auf den Beginn der Zeichenfolge oder des vorherigen führenden Bytes.

*current*<br/>
Zeiger auf die zu testende Zeichenfolgenposition.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_ismbslead** gibt-1 zurück, wenn das Zeichen ein führendes Byte ist und **_ismbstrail** gibt-1 zurück, wenn das Zeichen ein nachfolgendes Byte ist. Wenn die Eingabezeichenfolgen gültig sind, aber keine führenden oder nachfolgenden Bytes, geben diese Funktionen 0 zurück. Wenn ein Argument ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **NULL** und **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

**_ismbslead** und **_ismbstrail** sind langsamer als die **_ismbblead** und **_ismbbtrail** Versionen, da sie den Zeichenfolgenkontext berücksichtigen.

Die Versionen dieser Funktionen, die **_l** -Suffix sind beinahe identisch, außer dass für ihr vom Gebietsschema abhängiges Verhalten verwenden sie das Gebietsschema, das übergeben wird, anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> oder \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Für Manifestkonstanten für die Testbedingungen.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)<br/>
