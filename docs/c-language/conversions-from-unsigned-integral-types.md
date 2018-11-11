---
title: Konvertierungen von ganzzahligen Typen ohne Vorzeichen
ms.date: 01/29/2018
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: d7653c545601d10b159f10a8a3c8f60f9128f944
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579686"
---
# <a name="conversions-from-unsigned-integral-types"></a>Konvertierungen von ganzzahligen Typen ohne Vorzeichen

Eine ganze Zahl ohne Vorzeichen wird durch Abschneiden der höherwertigen Bits zu einer kürzeren Zahl ohne oder mit Vorzeichen konvertiert, oder sie wird durch Nullerweiterung in eine längere Zahl ohne oder mit Vorzeichen konvertiert (siehe Tabelle [Konvertierungen von ganzzahligen Typen ohne Vorzeichen](#_clang_table_4..3)).

Wenn der Ganzzahlwert in eine ganze Zahl mit Vorzeichen mit geringerer Größe tiefer gestuft wird, oder eine ganze Zahl ohne Vorzeichen in ihre entsprechende ganze Zahl mit Vorzeichen konvertiert wird, bleibt der Wert unverändert, wenn er im neuen Typ dargestellt werden kann. Der dargestellte Wert ändert sich jedoch, wenn wie im folgenden Beispiel das Vorzeichenbit festgelegt wird.

```C
int j;
unsigned short k = 65533;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

Wenn er nicht dargestellt werden kann, wird das Ergebnis durch die Implementierung definiert. Weitere Informationen zur Verarbeitung von tiefer gestuften Ganzzahlen durch den C-Compiler von Microsoft erhalten Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md). Eine ganzzahlige Konvertierung oder eine Typumwandlung der ganzen Zahl führen zum selben Verhalten.

Werte ohne Vorzeichen werden so konvertiert, dass sie ihren Wert beibehalten und nicht direkt in C darstellbar sind. Die einzige Ausnahme stellt eine Konvertierung von **unsigned long** in **float** dar, bei der höchstens die niederwertigen Bits verloren gehen. Andernfalls wird der Wert beibehalten, mit oder ohne Vorzeichen. Wenn ein Wert des ganzzahligen Typs in einen Gleitkommawert konvertiert wird, und der Wert außerhalb des darstellbaren Bereichs liegt, ist das Ergebnis nicht definiert. (Informationen über den Bereich für ganzzahlige Typen und Gleitkommatypen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).)

In der folgenden Tabelle werden die Konvertierungen von ganzzahligen Typen ohne Vorzeichen zusammengefasst.

## <a name="conversions-from-unsigned-integral-types"></a>Konvertierungen von integralen Typen ohne Vorzeichen

|Von|Beschreibung|Methode|
|----------|--------|------------|
|**unsigned char**|**char**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned char**|**short**|Nullerweiterung|
|**unsigned char**|**long**|Nullerweiterung|
|**unsigned char**|**unsigned short**|Nullerweiterung|
|**unsigned char**|**unsigned long**|Nullerweiterung|
|**unsigned char**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned char**|**double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned char**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned short**|**char**|Niederwertiges Byte beibehalten|
|**unsigned short**|**short**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned short**|**long**|Nullerweiterung|
|**unsigned short**|**unsigned char**|Niederwertiges Byte beibehalten|
|**unsigned short**|**unsigned long**|Nullerweiterung|
|**unsigned short**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned short**|**double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned short**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|
|**unsigned long**|**char**|Niederwertiges Byte beibehalten|
|**unsigned long**|**short**|Niederwertiges Wort beibehalten|
|**unsigned long**|**long**|Bitmuster wird beibehalten; oberes Bit wird Vorzeichenbit|
|**unsigned long**|**unsigned char**|Niederwertiges Byte beibehalten|
|**unsigned long**|**unsigned short**|Niederwertiges Wort beibehalten|
|**unsigned long**|**float**|Konvertieren in **long**; Konvertieren von **long** in **float**|
|**unsigned long**|**double**|Direktes Konvertieren in **double**|
|**unsigned long**|**long double**|Konvertieren in **long**; Konvertieren von **long** in **double**|

**Microsoft-spezifisch**

Der **unsigned int**-Typ entspricht für den Microsoft C-Compiler dem **unsigned long**-Typ. Die Konvertierung eines **unsigned int**-Werts wird auf dieselbe Weise wie die Konvertierung eines **unsigned long**-Werts ausgeführt. Konvertierungen von **unsigned long**-Werten in **float**-Werte sind nicht genau, wenn der Wert, der konvertiert wird, größer als der maximale positive **long**-Wert mit Vorzeichen ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Zuweisungskonvertierungen](../c-language/assignment-conversions.md)
