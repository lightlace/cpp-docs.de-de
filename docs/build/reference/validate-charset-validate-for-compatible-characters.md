---
title: /validate-charset (Auf kompatible Zeichen überprüfen)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: 2390aa98b9416eb538f529c8c370c888cccf4734
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498160"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (Auf kompatible Zeichen überprüfen)

Überprüft, ob der Text der Quelldatei nur Zeichen enthält, die als UTF-8 dargestellt werden können.

## <a name="syntax"></a>Syntax

```
/validate-charset[-]
```

## <a name="remarks"></a>Hinweise

Sie können die Option **/Validate-charset** verwenden, um zu überprüfen, ob der Quellcode nur Zeichen enthält, die sowohl im Quell Zeichensatz als auch im Ausführungs Zeichensatz dargestellt werden können. Diese Überprüfung wird automatisch aktiviert, wenn Sie die Compileroptionen **"/Source-charset"** , **"/Execution-charset"** oder **"/UTF-8"** angeben. Sie können diese Überprüfung explizit deaktivieren, indem Sie die **/Validate-charset-** -Option angeben.

Standardmäßig sucht Visual Studio nach einer Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in einem Unicode-Format codiert ist, z. B. UTF-16 oder UTF-8. Wenn keine Bytereihenfolge-Marke gefunden wurde, geht das Programm davon aus, dass die Quelldatei mithilfe der aktuellen Codepage des Benutzers codiert wurde, es sei denn, Sie haben mittels **/utf-8** oder **/Source-CharSet** eine Codepage spezifiziert. Visual Studio lässt zu, dass Sie Ihren C++-Quellcode mithilfe verschiedener Zeichencodierungen speichern. Weitere Informationen zu Quell- und Ausführungszeichensätzen finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Sprachdokumentation. Eine Liste der unterstützten Codepagebezeichner und Zeichensätze finden Sie unter [Code Page Identifiers (Codepagebezeichner)](/windows/win32/Intl/code-page-identifiers).

Visual Studio verwendet UTF-8 als interne Zeichencodierung während der Konvertierung zwischen dem Quell Zeichensatz und dem Ausführungs Zeichensatz. Wenn ein Zeichen in der Quelldatei nicht im Ausführungs Zeichensatz dargestellt werden kann, ersetzt die UTF-8-Konvertierung das Fragezeichen '? '. Die Option **/Validate-charset** bewirkt, dass die Kompilierung eine Warnung meldet, wenn dies auftritt.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie den Ordner **Konfigurations Eigenschaften**, **CC++/** und **Befehlszeile** .

1. Fügen Sie unter **zusätzliche Optionen**die Option **/Validate-charset** hinzu, und geben Sie Ihre bevorzugte Codierung an.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
["/Execution-charset" (Ausführungs Zeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)
