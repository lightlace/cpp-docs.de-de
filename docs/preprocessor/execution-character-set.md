---
title: execution_character_set
ms.date: 10/18/2018
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: bd31e8e91a1bcbfa6ace9b47fa2b13dd945adb20
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039925"
---
# <a name="executioncharacterset"></a>execution_character_set

Gibt an, die ausführungszeichengruppe für Zeichenfolgen- und Zeichenliterale verwendet. Diese Richtlinie ist für Literale, die mit dem Präfix U8 versehenes markiert nicht erforderlich.

## <a name="syntax"></a>Syntax

```
#pragma execution_character_set("target")
```

### <a name="parameters"></a>Parameter

*target*<br/>
Gibt den Zeichensatz der Ziel-Ausführung an. Derzeit ist die einzige zielausführung unterstützten festlegen "Utf-8".

## <a name="remarks"></a>Hinweise

Dieser Compiler-Anweisung ist veraltet ab Visual Studio 2015 Update 2. Wir empfehlen die Verwendung der `/execution-charset:utf-8` oder `/utf-8` Compileroptionen sowie mithilfe der `u8` Präfix für schmale Zeichen- und Zeichenfolgenliterale, die Sonderzeichen enthalten. Weitere Informationen zu den `u8` Präfix verwendet wird, finden Sie unter [Zeichenfolgen- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md). Weitere Informationen zu Compileroptionen finden Sie unter [/Execution-CharSet (Ausführungszeichensatz festlegen)](../build/reference/execution-charset-set-execution-character-set.md) und [/utf-8 (Quelle festlegen und ausführbare Datei legt in UTF-8-Zeichen)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

Die `#pragma execution_character_set("utf-8")` Anweisung teilt dem Compiler mit schmalen Zeichen und schmale Zeichenfolgenliterale in Ihrem Quellcode in die ausführbare Datei als UTF-8 codieren. Diese ausgabecodierung ist unabhängig von der Quelle verwendete dateicodierung.

Standardmäßig codiert der Compiler schmale Zeichen und schmalen Zeichenfolgen mithilfe der aktuellen Codepage als ausführungszeichensatz an. Dies bedeutet, dass Unicode oder in DBCS Zeichen in ein Literal, die außerhalb des Bereichs von der aktuellen Codepage sind in das standardersetzungszeichen in der Ausgabe konvertiert werden. Unicode- und DBCS-Zeichen werden auf deren niederwertige Byte abgeschnitten. Dies ist sicherlich nicht gewünscht. Sie können angeben, UTF-8-Codierung für Literale in der Quelldatei mit einer `u8` Präfix. Der Compiler übergibt diese UTF-8 codierte Zeichenfolgen unverändert in die Ausgabe an. Schmale Zeichenliterale, die mit dem Präfix U8 versehenes mit müssen in ein Byte passen, oder sie werden bei der Ausgabe abgeschnitten.

Standardmäßig verwendet Visual Studio die aktuelle Codepage als des quellzeichensatzes verwendet, um den Quellcode für die Ausgabe zu interpretieren. Wenn eine Datei gelesen wird, interpretiert Visual Studio es gemäß der aktuellen Codepage, es sei denn, die Codepage für die Datei festgelegt wurde, oder es sei denn, eine Bytereihenfolge-Marke (BOM) oder UTF-16-Zeichen am Anfang der Datei erkannt werden. Da UTF-8 nicht als die aktuelle Codepage festgelegt werden kann, wenn die automatische Erkennung Quelldateien, die codiert als UTF-8 ohne BOM stößt, nimmt Visual Studio an, dass sie mit der aktuellen Codepage codiert werden. Zeichen in der Quelldatei, die außerhalb des Bereichs des angegebenen oder automatisch erkannt werden, dass die Codepage Compiler-Warnungen und Fehler verursachen kann.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das \_ \_Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/UTF-8 (Quelle festlegen und ausführbare Zeichensätze auf UTF-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)