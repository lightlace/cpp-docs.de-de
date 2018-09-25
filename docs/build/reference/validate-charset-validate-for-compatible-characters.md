---
title: -Überprüfen-Charset (überprüfen nach kompatiblen Zeichen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 698a221dadf21e6d314f5556210d84b98853757f
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029527"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/ Validate-CharSet (überprüfen nach kompatiblen Zeichen)

Überprüft, ob der Quelltext für die Datei nur die darstellbare Zeichen enthält als UTF-8.

## <a name="syntax"></a>Syntax

```
/validate-charset[-]
```

## <a name="remarks"></a>Hinweise

Sie können die **/Validate-CharSet** Option aus, um sicherzustellen, dass der Quellcode enthält nur die Zeichen, die in beiden quellzeichensatzes dargestellt werden können und ausführungszeichensatz festgelegt. Diese Überprüfung wird automatisch aktiviert, bei der Angabe **/Source-CharSet**, **/Execution-CharSet**, oder **/utf-8** Compileroptionen. Sie können diese Prüfung explizit deaktivieren, durch Angabe der **/ validate-Charset -** Option.

Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei codiert mithilfe der aktuellen Codepage für Benutzer, es sei denn, Sie mithilfe eine Codepage angegeben haben **/utf-8** oder **/Source-CharSet** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Visual Studio verwendet UTF-8-zeichencodierung während der Konvertierung zwischen den Quell- und ausführungszeichensatz internen. Wenn ein Zeichen in der Quelldatei im ausführungszeichensatz dargestellt werden kann, ersetzt die UTF-8-Konvertierung durch ein Fragezeichen '?' Zeichen. Die **/Validate-CharSet** Option bewirkt, dass die Kompilierung an die eine Warnung ausgeben, wenn dies der Fall.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **erweiterte Optionen**, Hinzufügen der **/Validate-CharSet** aus, und geben Sie Ihre bevorzugten Codierung.

1. Wählen Sie **OK** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)