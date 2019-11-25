---
title: Gebietsschemas und Codepages
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], about locales
- locale IDs [C++]
- locales [C++]
- code pages [C++]
- code pages [C++], dynamically changing
- character sets [C++], code pages
- multibyte code pages [C++]
- character sets [C++], locales
- localization [C++], code pages
- localization [C++], locales
- code pages [C++], locales
- conventions [C++], international character support
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
ms.openlocfilehash: 5821048363d92911f2902a580cb11f5b349f5e7c
ms.sourcegitcommit: 4f15b69e35dd112001b24fe9dc836dd5d6902465
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2019
ms.locfileid: "74474072"
---
# <a name="locales-and-code-pages"></a>Gebietsschemas und Codepages

Eine Gebietsschema-ID spiegelt die lokalen Konventionen sowie die Sprache eines bestimmten geografischen Bereichs wider. Viele Sprachen werden in mehreren Ländern/Regionen gesprochen, z. B. wird Portugiesisch in Brasilien und Portugal gesprochen. Umgekehrt gibt es in einem Land/einer Region möglicherweise mehrere Amtssprachen. In Kanada gibt es z. B. zwei Amtssprachen: Englisch und Französisch. Für Kanada gibt es foglich zwei unterschiedliche Gebietsschemas: Englisch (Kanada) und Französisch (Kanada). Vom Gebietsschema abhängig sind u. a. Datumsformat und Währungsformat.

Durch die Sprache werden die Konventionen für die Text- und Datenformatierung bestimmt, während durch das Land/die Region die länderspezifischen Konventionen festlegt werden. Jede Sprache weist eine eindeutige, durch Codepages dargestellte Zuordnung auf, in der Zeichen enthalten sind, die nicht im Alphabet vorkommen (z. B. Satzzeichen und Zahlen). Bei einer Codepage handelt es sich um einen Zeichensatz; sie ist mit der Sprache verknüpft. As such, a [locale](../c-runtime-library/locale.md) is a unique combination of language, country/region, and code page. The locale and code page setting can be changed at run time by calling the [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) function.

Von unterschiedlichen Sprachen werden möglicherweise unterschiedliche Codepages verwendet. Die ANSI-Codepage 1252 wird z. B. für Englisch und die meisten europäischen Sprachen verwendet, während die ANSI-Codepage 932 für das japanische Kanji eingesetzt wird. Nahezu alle Codepages verwenden für die ersten 128 Zeichen (0 x 00 to 0 x 7 F) den ASCII-Zeichensatz.

Jede Einzelbyte-Codepage kann in einer Tabelle (mit 256 Einträgen) als Zuordnung von Bytewerten zu Zeichen (einschließlich Ziffern und Satzzeichen) oder Symbolen dargestellt werden. Jede Mehrbyte-Codepage kann ebenfalls als umfangreiche Tabelle (mit Einträgen im Umfang von 64 KB) dargestellt werden, in der Doppelbytewerte Zeichen zugeordnet werden. In practice, however, it is usually represented as a table for the first 256 (single-byte) characters and as ranges for the double-byte values.

Weitere Informationen zu Codepages finden Sie unter [Codepages](../c-runtime-library/code-pages.md).

Die C-Laufzeitbibliothek weist zwei Arten interner Codepages auf: die Gebietsschema-Codepage und die Mehrbyte-Codepage. You can change the current code page during program execution (see the documentation for the [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) and [_setmbcp](../c-runtime-library/reference/setmbcp.md) functions). Also, the run-time library might obtain and use the value of the operating system code page, which is constant for the duration of the program's execution.

Wenn sich die Codepage eines Gebietsschemas ändert, ändert sich das Verhalten der vom jeweiligen Gebietsschema abhängigen Funktionen gemäß des von der ausgewählten Codepage vorgegebenen Verhaltens. Standardmäßig beginnen alle vom Gebietsschema abhängigen Funktionen die Ausführung mit einer Gebietsschema-Codepage, die für das "C"-Gebietsschema eindeutig ist. Sie können die interne Codepage für das Gebietsschema (ebenso wie andere Gebietsschema-spezifische Eigenschaften) durch Aufruf der `setlocale`-Funktion ändern. Durch den Aufruf von `setlocale`(LC_ALL, "") wird das Gebietsschema gemäß den Vorgaben für das Gebietsschema des Benutzers des Betriebssystem eingestellt.

Wenn sich die Mehrbyte-Codepage ändert, ändert sich entsprechend das Verhalten der Mehrbytefunktionen gemäß des von der ausgewählten Codepage vorgegebenen Verhaltens. Standardmäßig beginnen alle Mehrbytefunktionen die Ausführung mit der Mehrbyte-Codepage, die der Standard-Codepage des Betriebssystems entspricht. Sie können die interne Mehrbyte-Codepage durch Aufruf der `_setmbcp`-Funktion ändern.

Mit der C-Laufzeitbibliotheksfunktion `setlocale` können Sie alle Gebietsschemainformationen des aktuellen Programms oder Teile davon einstellen, ändern und abfragen. The [_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) routine is a wide-character version of `setlocale`; the arguments and return values of `_wsetlocale` are wide-character strings.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Vorteile der Zeichensatzportabilität](../text/benefits-of-character-set-portability.md)
