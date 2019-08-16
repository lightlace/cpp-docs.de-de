---
title: /UTF-8 (Festlegen von Quell- und Ausführungszeichensätze auf UTF-8)
title: /UTF-8 (Festlegen von Quell- und Ausführungszeichensätze auf UTF-8)

ms.date: 11/04/2016
f1_keywords:
- /utf-8
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
ms.openlocfilehash: 1ff0f23ad0758642c73b1b35d6d4dd1be20899cb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498181"
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (Festlegen von Quell- und Ausführungszeichensätze auf UTF-8)

Gibt sowohl den Quell- als auch den Ausführungszeichensatz als UTF-8 an.

## <a name="syntax"></a>Syntax

```
/utf-8
```

## <a name="remarks"></a>Hinweise


Sie können **/utf-8** verwenden, um festzulegen, dass sowohl der Quell- als auch der Ausführungszeichensatz mittels UTF-8 codiert ist. Diese Option ist äquivalent zu **/source-Charset:utf-8** und **/execution-Charset:utf-8** in der Befehlszeile. Jede dieser Optionen aktiviert automatisch auch **/Validate-CharSet**. Eine Liste der unterstützten Codepagebezeichner und Zeichensätze finden Sie unter [Code Page Identifiers (Codepagebezeichner)](/windows/desktop/Intl/code-page-identifiers).


Standardmäßig sucht Visual Studio nach einer Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in einem Unicode-Format codiert ist, z. B. UTF-16 oder UTF-8. Wenn keine Bytereihenfolge-Marke gefunden wurde, geht das Programm davon aus, dass die Quelldatei mithilfe der aktuellen Codepage des Benutzers codiert wurde, es sei denn, Sie haben mittels **/utf-8** oder **/Source-CharSet** eine Codepage spezifiziert. Visual Studio lässt zu, dass Sie Ihren C++-Quellcode mithilfe verschiedener Zeichencodierungen speichern. Weitere Informationen zu Quell- und Ausführungszeichensätzen finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Sprachdokumentation.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie den Ordner **Konfigurations Eigenschaften**, **CC++/** und **Befehlszeile** .


1. Fügen Sie unter **Zusätzliche Optionen** den Eintrag "**/utf-8**" hinzu, um UTF-8 als bevorzugte Codierung anzugeben.


1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
["/Execution-charset" (Ausführungs Zeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
