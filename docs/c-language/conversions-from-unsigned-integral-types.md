---
title: Konvertierungen von integralen Typen ohne Vorzeichen
ms.date: 10/02/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: 3099f0113103223e392dc20560899b4a6e3ebf20
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998788"
---
# <a name="conversions-from-unsigned-integral-types"></a>Konvertierungen von integralen Typen ohne Vorzeichen

Wenn eine ganze Zahl ohne Vorzeichen in eine Ganzzahl oder einen Gleit kommatyp konvertiert wird, wird der Wert unverändert geändert, wenn der ursprüngliche Wert im Ergebnistyp dargestellt werden kann.

Beim Umrechnen einer Ganzzahl ohne Vorzeichen in eine Ganzzahl mit größerer Größe wird der Wert mit 0 (null) erweitert. Bei der Umstellung auf eine Ganzzahl kleiner, werden die höherwertigen Bits abgeschnitten. Das Ergebnis wird mit dem Ergebnistyp interpretiert, wie in diesem Beispiel gezeigt.

```C
unsigned k = 65533;
short j;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

Beim Umrechnen einer Ganzzahl ohne Vorzeichen in einen Gleit kommatyp ist das Ergebnis der nächsthöhere oder niedrigere darstellbare Wert, wenn der ursprüngliche Wert nicht exakt im Ergebnistyp dargestellt werden kann.

Informationen zu den Größen von ganzzahligen und Gleit Komma Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md) .

**Microsoft-spezifisch**

Im Microsoft-Compiler sind **Ganzzahl ohne Vorzeichen** (oder **Ganzzahl ohne Vorzeichen int**) und **Ganzzahl ohne Vorzeichen long** eindeutig, aber äquivalente Typen. Die Konvertierung eines **unsigned int**-Werts wird auf dieselbe Weise wie die Konvertierung eines **unsigned long**-Werts ausgeführt.

**Ende Microsoft-spezifisch**

In der folgenden Tabelle werden die Konvertierungen von ganzzahligen Typen ohne Vorzeichen zusammengefasst.

## <a name="table-of-conversions-from-unsigned-integral-types"></a>Tabelle mit Konvertierungen von ganzzahligen Typen ohne Vorzeichen

|Von|Beschreibung|Methode|
|----------|--------|------------|
|**unsigned char**|**char**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned char**|**short**|Nullerweiterung|
|**unsigned char**|**long**|Nullerweiterung|
|**unsigned char**|**langes long**|Nullerweiterung|
|**unsigned char**|**unsigned short**|Nullerweiterung|
|**unsigned char**|**unsigned long**|Nullerweiterung|
|**unsigned char**|**Ganzzahl ohne Vorzeichen long long**|Nullerweiterung|
|**unsigned char**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned char**|**double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned char**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned short**|**char**|Niederwertiges Byte beibehalten|
|**unsigned short**|**short**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned short**|**long**|Nullerweiterung|
|**unsigned short**|**langes long**|Nullerweiterung|
|**unsigned short**|**unsigned char**|Niederwertiges Byte beibehalten|
|**unsigned short**|**unsigned long**|Nullerweiterung|
|**unsigned short**|**Ganzzahl ohne Vorzeichen long long**|Nullerweiterung|
|**unsigned short**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned short**|**double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned short**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned long**|**char**|Niederwertiges Byte beibehalten|
|**unsigned long**|**short**|Niederwertiges Wort beibehalten|
|**unsigned long**|**long**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned long**|**langes long**|Nullerweiterung|
|**unsigned long**|**unsigned char**|Niederwertiges Byte beibehalten|
|**unsigned long**|**unsigned short**|Niederwertiges Wort beibehalten|
|**unsigned long**|**Ganzzahl ohne Vorzeichen long long**|Nullerweiterung|
|**unsigned long**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned long**|**double**|Direktes Konvertieren in **double**|
|**unsigned long**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**Ganzzahl ohne Vorzeichen long long**|**char**|Niederwertiges Byte beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**short**|Niederwertiges Wort beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**long**|DWORD mit niedriger Reihenfolge beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**langes long**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**Ganzzahl ohne Vorzeichen long long**|**unsigned char**|Niederwertiges Byte beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**unsigned short**|Niederwertiges Wort beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**unsigned long**|DWORD mit niedriger Reihenfolge beibehalten|
|**Ganzzahl ohne Vorzeichen long long**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**Ganzzahl ohne Vorzeichen long long**|**double**|Direktes Konvertieren in **double**|
|**Ganzzahl ohne Vorzeichen long long**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|

## <a name="see-also"></a>Siehe auch

[Zuweisungs Konvertierungen](../c-language/assignment-conversions.md)
