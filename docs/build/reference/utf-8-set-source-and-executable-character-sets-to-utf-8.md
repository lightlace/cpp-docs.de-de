---
title: /UTF-8 (Quell- und Ausführungszeichensätze auf UTF-8 festlegen)
ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 5ac15c63041e76b8bb0d292868bb982c21866078
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317288"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (Quell- und Ausführungszeichensätze auf UTF-8 festlegen)

Legt sowohl den Quell- als auch den Ausführungszeichensatz auf UTF-8 fest.

## <a name="syntax"></a>Syntax

```
/utf-8
```

## <a name="remarks"></a>Hinweise

Sie können **/utf-8** verwenden, um festzulegen, dass Quell- und Ausführungszeichensatz mittels UTF-8 codiert sind. Diese Option ist äquivalent zu **/source-Charset:utf-8** und **/execution-Charset:utf-8** in der Befehlszeile. Jede dieser Optionen aktiviert automatisch auch **/Validate-CharSet**. Eine Liste der unterstützten Codepage-Identifiers und Zeichensätze finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Standardmäßig sucht Visual Studio nach einer Byte-Order-Markierung, um festzustellen, ob die Quelldatei in einem Unicode-Format kodiert ist, z. B. UTF-16 oder UTF-8. Wenn keine Byte-Order-Markierung gefunden wurde, geht das Programm davon aus, dass die Quelldatei mithilfe der aktuellen Codepage des Benutzers kodiert wurde, es sei denn, Sie haben mittels **/utf-8** oder **/Source-CharSet** eine Codepage spezifiziert. Visual Studio erlaubt es Ihnen Ihren C++-Quellcode mithilfe  verschiedener Zeichenkodierungen zu speichern. Weitere Informationen zu Quell- und Ausführungszeichensätzen finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Sprachdokumentation.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projektes. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **Zusätzliche Optionen**, den Eintrag "**/utf-8**" hinzufügen, um UTF-8 als bevorzugte Kodierung anzugeben.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
