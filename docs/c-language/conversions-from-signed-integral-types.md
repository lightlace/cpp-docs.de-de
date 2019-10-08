---
title: Konvertierungen von ganzzahligen Typen mit Vorzeichen
ms.date: 10/02/2019
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: 79608b5ca4335ee3c30bdab27e7efade5b7e2f54
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998726"
---
# <a name="conversions-from-signed-integral-types"></a>Konvertierungen von ganzzahligen Typen mit Vorzeichen

Wenn eine ganze Zahl mit Vorzeichen in eine ganze Zahl oder einen Gleit kommatyp konvertiert wird, wird der Wert unverändert geändert, wenn der ursprüngliche Wert im Ergebnistyp dargestellt werden kann.

Wenn eine ganze Zahl mit Vorzeichen in eine Ganzzahl mit größerer Größe konvertiert wird, wird der Wert mit Vorzeichen erweitert. Bei der Konvertierung in eine ganze Zahl kleiner, werden die höherwertigen Bits abgeschnitten. Das Ergebnis wird mit dem Ergebnistyp interpretiert, wie im folgenden Beispiel gezeigt:

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

Beim Umrechnen einer Ganzzahl mit Vorzeichen in einen Gleit kommatyp ist das Ergebnis der nächsthöhere oder niedrigere darstellbare Wert, wenn der ursprüngliche Wert nicht exakt im Ergebnistyp dargestellt werden kann.

Informationen zu den Größen von ganzzahligen und Gleit Komma Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).

In der folgenden Tabelle sind die Konvertierungen von ganzzahligen Typen mit Vorzeichen zusammengefasst. Dabei wird davon ausgegangen, dass der **char** -Typ standardmäßig signiert ist. Wenn Sie eine Kompilierzeit Option verwenden, um den Standardwert für den Typ " **char** " in "Ganzzahl ohne Vorzeichen" zu ändern, gelten die Konvertierungen aus der Tabelle [Konvertierungen aus](../c-language/conversions-from-unsigned-integral-types.md) ganzzahligen Typen ohne Vorzeichen für den **unsignierten char** -Typ anstelle der Konvertierungen in dieser Tabelle.

**Microsoft-spezifisch**

Im Microsoft-Compiler sind " **int** " und " **Long** " eindeutige, aber äquivalente Typen. Die Konvertierung eines **int** -Werts erfolgt auf dieselbe Weise wie die Konvertierung eines **Long**-Werts.

**Ende Microsoft-spezifisch**

## <a name="table-of-conversions-from-signed-integral-types"></a>Tabelle mit Konvertierungen von ganzzahligen Typen mit Vorzeichen

|Von|Beschreibung|Methode|
|----------|--------|------------|
|**char**<sup>1</sup>|**short**|Signaturerweiterung|
|**char**|**long**|Signaturerweiterung|
|**char**|**langes long**|Signaturerweiterung|
|**char**|**unsigned char**|Muster beibehalten; oberes Bit verliert Funktion als Vorzeichenbit|
|**char**|**unsigned short**|Signaturerweiterung auf **short**; Konvertieren von **short** in **unsigned short**|
|**char**|**unsigned long**|Signaturerweiterung auf **long**; Konvertieren von **long** in **unsigned long**|
|**char**|**Ganzzahl ohne Vorzeichen long long**|Signatur Erweiterung auf **Long Long**; Konvertieren von **Long Long** in **Ganzzahl ohne Vorzeichen long long**|
|**char**|**float**|Signaturerweiterung auf **long**; Konvertieren von **long** in **float**|
|**char**|**double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|
|**char**|**long double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|
|**short**|**char**|Niederwertiges Byte beibehalten|
|**short**|**long**|Signaturerweiterung|
|**short**|**langes long**|Signaturerweiterung|
|**short**|**unsigned char**|Niederwertiges Byte beibehalten|
|**short**|**unsigned short**|Bitmuster beibehalten; höherwertiges Bit verliert Funktion als Vorzeichenbit|
|**short**|**unsigned long**|Signaturerweiterung auf **long**; Konvertieren von **long** in **unsigned long**|
|**short**|**Ganzzahl ohne Vorzeichen long long**|Signatur Erweiterung auf **Long Long**; Konvertieren von **Long Long** in **Ganzzahl ohne Vorzeichen long long**|
|**short**|**float**|Signaturerweiterung auf **long**; Konvertieren von **long** in **float**|
|**short**|**double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|
|**short**|**long double**|Signaturerweiterung auf **long**; Konvertieren von **long** in **double**|
|**long**|**char**|Niederwertiges Byte beibehalten|
|**long**|**short**|Niederwertiges Wort beibehalten|
|**long**|**langes long**|Signaturerweiterung|
|**long**|**unsigned char**|Niederwertiges Byte beibehalten|
|**long**|**unsigned short**|Niederwertiges Wort beibehalten|
|**long**|**unsigned long**|Bitmuster beibehalten; höherwertiges Bit verliert Funktion als Vorzeichenbit|
|**long**|**Ganzzahl ohne Vorzeichen long long**|Signatur Erweiterung auf **Long Long**; Konvertieren von **Long Long** in **Ganzzahl ohne Vorzeichen long long**|
|**long**|**float**|Darstellen als **float**. Wenn **Long** nicht genau dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|
|**long**|**double**|Darstellen als **double**. Wenn **Long** nicht genau als **Double**dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|
|**long**|**long double**|Darstellen als **double**. Wenn **Long** nicht genau als **Double**dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|
|**langes long**|**char**|Niederwertiges Byte beibehalten|
|**langes long**|**short**|Niederwertiges Wort beibehalten|
|**langes long**|**long**|DWORD mit niedriger Reihenfolge beibehalten|
|**langes long**|**unsigned char**|Niederwertiges Byte beibehalten|
|**langes long**|**unsigned short**|Niederwertiges Wort beibehalten|
|**langes long**|**unsigned long**|DWORD mit niedriger Reihenfolge beibehalten|
|**langes long**|**Ganzzahl ohne Vorzeichen long long**|Bitmuster beibehalten; höherwertiges Bit verliert Funktion als Vorzeichenbit|
|**langes long**|**float**|Darstellen als **float**. Wenn **Long Long** nicht exakt dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|
|**langes long**|**double**|Darstellen als **double**. Wenn **Long Long** nicht genau als **Double**dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|
|**langes long**|**long double**|Darstellen als **double**. Wenn **Long Long** nicht genau als **Double**dargestellt werden kann, geht eine gewisse Genauigkeit verloren.|

<sup>1</sup> bei allen **char** -Einträgen wird davon ausgegangen, dass der **char** -Typ standardmäßig signiert ist.

## <a name="see-also"></a>Siehe auch

[Zuweisungs Konvertierungen](../c-language/assignment-conversions.md)
