---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 11/04/2016
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
ms.openlocfilehash: 059d0781e465f6491f27fd634bbc4479104bc12f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331297"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l

Vergleicht **n** Bytes von zwei Multibyte-Zeichenfolgen und ignoriert Groß-/Kleinschreibung.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Parameter

*string1*, *string2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen.

*count*<br/>
Anzahl der zu vergleichenden Bytes.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt die Beziehung zwischen den untergeordneten Zeichenfolgen an.

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|*Zeichenfolge1* Teilzeichenfolge höchstens *Zeichenfolge2* Teilzeichenfolge.|
|0|*Zeichenfolge1* identisch *Zeichenfolge2* Teilzeichenfolge.|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2* Teilzeichenfolge.|

Bei einem Fehler **_mbsnbicmp** gibt **_NLSCMPERROR**, definiert in String.h und Mbstring.h.

## <a name="remarks"></a>Hinweise

Die **_mbsnbicmp** -Funktion führt einen Ordinalvergleich von höchstens der ersten *Anzahl* Bytes *string1* und *Zeichenfolge2*. Der Vergleich wird ausgeführt, indem jedes Zeichen in Kleinbuchstaben konvertiert werden; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) ist eine Groß-/Kleinschreibung Version **_mbsnbicmp**. Der Vergleich endet, wenn ein abschließendes Nullzeichen, in jeder Zeichenfolge vor dem erreicht ist *Anzahl* Zeichen verglichen wurden. Wenn die Zeichenfolgen gleich sind. wenn ein abschließendes Nullzeichen erreicht ist in jeder Zeichenfolge vor dem *Anzahl* Zeichen verglichen wurden, die kürzere Zeichenfolge kleiner ist.

**_mbsnbicmp** ähnelt [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md), außer dass es bis zu Zeichenfolgen vergleicht *Anzahl* Bytes anstatt Zeichen.

Abhängig von der Großschreibung ist der Vergleich von zwei Zeichenfolgen mit Zeichen zwischen „Z“ und „a“ in der ASCII-Tabelle ('[', '\\', ']', '^', '_' und '\`') unterschiedlich. Z. B. die beiden Zeichenfolgen "ABCDE" und "ABCD ^" eine Richtung verglichen, wenn Kleinschreibung vorliegt ("Abcde" > "Abcd ^") und die andere Möglichkeit ("ABCDE" < "ABCD ^"), wenn Großschreibung vorliegt.

**_mbsnbicmp** erkennt multibytezeichensequenzen gemäß der [multibyte-Codepage](../../c-runtime-library/code-pages.md) aktuell. Die aktuelle Gebietsschemaeinstellung nimmt dabei keinen Einfluss.

Wenn entweder *string1* oder *Zeichenfolge2* ist ein null-Zeiger **_mbsnbicmp** ruft der Handler für ungültige Parameter wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **_NLSCMPERROR** und **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel [_mbsnbcmp _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
