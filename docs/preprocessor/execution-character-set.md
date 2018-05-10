---
title: Execution_character_set | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
dev_langs:
- C++
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6cb84ae6ffebda3dd335bc001463e2d8579f99
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="executioncharacterset"></a>execution_character_set
Gibt die ausführungszeichengruppe für Zeichenfolgen- und Zeichenliterale verwendet. Diese Direktive ist für Literale, die mit dem Präfix u8 markiert nicht erforderlich.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma execution_character_set("target")  
```  
  
#### <a name="parameters"></a>Parameter  
 `target`  
 Gibt die Ziel-ausführungszeichensatzes an. Derzeit ist die einzige zielausführung legen Sie unterstützten "Utf-8".  
  
## <a name="remarks"></a>Hinweise  
 Dieser Compiler-Direktive ist veraltet ab Visual Studio 2015 Update 2. Wir empfehlen die Verwendung der **/execution-Charset:utf-8** oder **/utf-8** Compileroptionen zusammen mit der Verwendung der `u8` Präfix für schmale Zeichen- und Zeichenfolgenliterale, die enthalten erweiterte Zeichen. Weitere Informationen zu den `u8` Präfix verwendet wird, finden Sie unter [Zeichenfolgen- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md). Weitere Informationen zu Compileroptionen finden Sie unter [/execution-charset (Festlegen der Ausführung-Zeichensatz)](../build/reference/execution-charset-set-execution-character-set.md) und [/utf-8 (Quelle festlegen und ausführbare Datei legt in UTF-8-Zeichen)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md).  
  
 Die `#pragma execution_character_set("utf-8")` Richtlinie teilt dem Compiler mit schmalen Zeichen und schmale Zeichenfolgenliterale in Ihrem Quellcode in die ausführbare Datei als UTF-8 codieren. Diese ausgabecodierung ist unabhängig von der quelldateicodierung verwendet.  
  
 Standardmäßig codiert der Compiler schmalen Zeichen und schmalen Zeichenfolgen mithilfe der aktuellen Codepage als die ausführungszeichengruppe an. Dies bedeutet, dass Unicode oder DBCS-Zeichen in ein Literal werden außerhalb des Bereichs von der aktuellen Codepage enthalten sind, in das standardersetzungszeichen in der Ausgabe konvertiert werden. Unicode- und DBCS-Zeichen werden auf ihre niederwertige Byte abgeschnitten. Dies ist mit großer Wahrscheinlichkeit nicht gewünscht. Sie können angeben, UTF-8-Codierung für Literale in der Quelldatei mit einer `u8` Präfix. Der Compiler übergibt diese UTF-8 codierte Zeichenfolgen unverändert an die Ausgabe an. Mit dem Präfix u8 mit schmale Zeichenliterale müssen in ein Byte passen oder sie werden bei der Ausgabe abgeschnitten.  
  
 Standardmäßig verwendet Visual Studio die aktuelle Codepage als die Quelle-Zeichensatz, der zum Interpretieren von Quellcode für die Ausgabe an. Wenn in eine Datei schreibgeschützt ist, interpretiert Visual Studio es entsprechend der aktuellen Codepage, es sei denn, die Codepage der Datei festgelegt wurde, oder es sei denn, eine Bytereihenfolge-Marke (BOM) oder UTF-16-Zeichen am Anfang der Datei erkannt werden. Da UTF-8 stößt die automatische Erkennung Quelldateien codiert als UTF-8 ohne eine BOM als die aktuelle Codepage festgelegt werden kann, wird Visual Studio davon ausgegangen, dass sie mit der aktuellen Codepage codiert werden. Zeichen in der Quelldatei, die außerhalb des Bereichs des angegebenen oder automatisch erkannt werden, dass die Codepage Compiler-Warnungen und Fehler verursachen kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/Execution-CharSet (Festlegen der Ausführung-Zeichensatz)](../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)