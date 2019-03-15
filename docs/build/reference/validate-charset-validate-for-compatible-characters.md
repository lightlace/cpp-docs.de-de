---
title: / Validate-CharSet (überprüfen nach kompatiblen Zeichen)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: 30c818bcb64c2f2ee57c05a4870e7d30afe98cfe
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810067"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **zusätzliche Optionen**, Hinzufügen der **/Validate-CharSet** aus, und geben Sie Ihre bevorzugten Codierung.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
