---
title: execution_character_set-Pragma
ms.date: 08/29/2019
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: 0c2c812f27634f397af91eace7a41c0e71c1eb99
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218624"
---
# <a name="execution_character_set-pragma"></a>execution_character_set-Pragma

Gibt den für Zeichen folgen-und Zeichen Literale verwendeten Ausführungs Zeichensatz an. Diese Direktive wird nicht für Literale benötigt, die `u8` mit dem Präfix gekennzeichnet sind.

## <a name="syntax"></a>Syntax

> **#pragma execution_character_set (** "*target*" **)**

### <a name="parameters"></a>Parameter

*Spar*\
Gibt den Ziel Ausführungs Zeichensatz an. Derzeit wird nur "UTF-8" als Ziel Ausführungs Satz unterstützt.

## <a name="remarks"></a>Hinweise

Diese Compilerdirektive ist veraltet, beginnend mit Visual Studio 2015 Update 2. Es wird empfohlen, die `/execution-charset:utf-8` Compileroptionen oder `/utf-8` mit dem `u8` Präfix für schmale Zeichen-und Zeichen folgen Literale zu verwenden, die erweiterte Zeichen enthalten. Weitere Informationen `u8` zum Präfix finden Sie unter [Zeichen folgen-und Zeichen Literale](../cpp/string-and-character-literals-cpp.md). Weitere Informationen zu den Compileroptionen finden Sie unter ["/Execution-charset" (Set Execution Character Set)](../build/reference/execution-charset-set-execution-character-set.md) und ["/UTF-8" (Festlegen von Quell-und ausführbaren Zeichensätzen auf UTF-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).

Die `#pragma execution_character_set("utf-8")` -Direktive weist den Compiler an, schmale Zeichen und schmale Zeichen folgen Literale in Ihrem Quellcode als UTF-8 in der ausführbaren Datei zu codieren. Diese Ausgabe Codierung ist unabhängig von der verwendeten Quelldatei Codierung.

Standardmäßig codiert der Compiler schmale Zeichen und schmale Zeichen folgen mithilfe der aktuellen Codepage als Ausführungs Zeichensatz. Dies bedeutet, dass Unicode-oder DBCS-Zeichen in einem Literalzeichen, die sich außerhalb des Bereichs der aktuellen Codepage befinden, in das Standard Ersetzungs Zeichen in der Ausgabe konvertiert werden. Unicode-und DBCS-Zeichen werden auf das nieder wertige Byte gekürzt. Dies ist fast sicherlich nicht das, was Sie beabsichtigen. Sie können die UTF-8-Codierung für Literale in der Quelldatei angeben, `u8` indem Sie ein Präfix verwenden. Der Compiler übergibt diese UTF-8-codierten Zeichen folgen unverändert an die Ausgabe. Schmale Zeichen Literale, die mithilfe von U8 als Präfix versehen sind, müssen in ein Byte passen, oder Sie werden bei der Ausgabe abgeschnitten.

Standardmäßig verwendet Visual Studio die aktuelle Codepage als Quell Zeichensatz, der zum Interpretieren des Quellcodes für die Ausgabe verwendet wird. Wenn eine Datei eingelesen wird, interpretiert Visual Studio Sie entsprechend der aktuellen Codepage, es sei denn, die Datei Codepage wurde festgelegt, oder es wird nur eine Byte Reihenfolge Markierung (BOM) oder UTF-16-Zeichen am Anfang der Datei erkannt. Da UTF-8 nicht als aktuelle Codepage festgelegt werden kann, geht Visual Studio davon aus, dass Sie mithilfe der aktuellen Codepage codiert werden, wenn die automatische Erkennung Quelldateien findet, die als UTF-8 codiert sind. Zeichen in der Quelldatei, die sich außerhalb des Bereichs der angegebenen oder automatisch erkannten Codepage befinden, können Compilerwarnungen und-Fehler verursachen.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven \_und das \_Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
["/Execution-charset" (Ausführungs Zeichensatz festlegen)](../build/reference/execution-charset-set-execution-character-set.md)\
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
