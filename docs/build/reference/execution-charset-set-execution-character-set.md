---
title: "\"/Execution-charset\" (Ausführungs Zeichensatz festlegen)"
ms.date: 02/06/2019
f1_keywords:
- execution-charset
- /execution-charset
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
ms.openlocfilehash: 44e83524867bc8a914706e1f5b45b61bc4a48087
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492913"
---
# <a name="execution-charset-set-execution-character-set"></a>"/Execution-charset" (Ausführungs Zeichensatz festlegen)

Ermöglicht das Angeben des Ausführungs Zeichensatzes für die ausführbare Datei.

## <a name="syntax"></a>Syntax

```
/execution-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Argumente

*IANA_name*<br/>
Der IANA-definierte Zeichensatz Name.

*CPID*<br/>
Der Code Page Bezeichner.

## <a name="remarks"></a>Hinweise

Sie können die **"/Execution-charset"** -Option verwenden, um einen Ausführungs Zeichensatz anzugeben. Der Ausführungs Zeichensatz ist die Codierung, die für den Text des Programms verwendet wird, der nach allen Vorverarbeitungs Schritten in die Kompilierungs Phase eingegeben wird. Dieser Zeichensatz wird für die interne Darstellung von Zeichen folgen-oder Zeichen Literalen im kompilierten Code verwendet. Legen Sie diese Option fest, um den erweiterten Ausführungs Zeichensatz anzugeben, der verwendet werden soll, wenn die Quelldateien Zeichen enthalten, die im grundlegenden Ausführungs Zeichensatz nicht Darstell Bar sind. Sie können entweder den IANA-oder ISO-Zeichensatz Namen oder einen Punkt (.) gefolgt von einem 3 bis 5 stelligen Dezimaltrennzeichen-Code Page Bezeichner verwenden, um den zu verwendenden Zeichensatz anzugeben. Eine Liste der unterstützten Codepagebezeichner und Zeichensätze finden Sie unter [Code Page Identifiers (Codepagebezeichner)](/windows/win32/Intl/code-page-identifiers).

Standardmäßig sucht Visual Studio nach einer Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in einem Unicode-Format codiert ist, z. B. UTF-16 oder UTF-8. Wenn keine Byte Reihenfolge Markierung gefunden wird, wird davon ausgegangen, dass die Quelldatei mithilfe der aktuellen Benutzer Codepage codiert wird, es sei denn, Sie haben mithilfe der **"/Source-charset"** -Option oder der **"/UTF-8"** -Option einen Zeichensatz Namen oder eine Codepage angegeben. Visual Studio lässt zu, dass Sie Ihren C++-Quellcode mithilfe verschiedener Zeichencodierungen speichern. Weitere Informationen zu Quell- und Ausführungszeichensätzen finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Sprachdokumentation.

Wenn Sie den Quell Zeichensatz und den Ausführungs Zeichensatz auf UTF-8 festlegen möchten, können Sie die **"/UTF-8"** -Compileroption als Verknüpfung verwenden. Diese Option ist äquivalent zu **/source-Charset:utf-8 und /execution-Charset:utf-8** in der Befehlszeile. Jede dieser Optionen aktiviert automatisch auch **/Validate-CharSet**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie den Ordner **Konfigurations Eigenschaften**, **CC++/** und **Befehlszeile** .

1. Fügen Sie unter **zusätzliche Optionen**die Option **"/Execution-charset"** hinzu, und geben Sie Ihre bevorzugte Codierung an.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/source-charset (Quellzeichensatz festlegen)](source-charset-set-source-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
