---
title: "\"/Source-charset\" (Quell Zeichensatz festlegen)"
ms.date: 02/06/2019
f1_keywords:
- source-charset
- /source-charset
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
ms.openlocfilehash: cd3e4eb3fd305ba6bdd298d18b1edb80f2b98343
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498259"
---
# <a name="source-charset-set-source-character-set"></a>"/Source-charset" (Quell Zeichensatz festlegen)

Ermöglicht das Angeben des Quell Zeichensatzes für die ausführbare Datei.

## <a name="syntax"></a>Syntax

```
/source-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Argumente

**IANA_name**<br/>
Der IANA-definierte Zeichensatz Name.

**CPID**<br/>
Der Code Page Bezeichner als Dezimalzahl.

## <a name="remarks"></a>Hinweise

Sie können die **"/Source-charset"** -Option verwenden, um einen erweiterten Quell Zeichensatz anzugeben, der verwendet werden soll, wenn die Quelldateien Zeichen enthalten, die nicht im grundlegenden Quell Zeichensatz dargestellt werden. Der Quell Zeichensatz ist die Codierung, die verwendet wird, um den Quelltext des Programms in die interne Darstellung zu interpretieren, die vor der Kompilierung als Eingabe für die Vorverarbeitungs Phasen verwendet wird. Die interne Darstellung wird dann in den Ausführungs Zeichensatz konvertiert, um Zeichen folgen-und Zeichen Werte in der ausführbaren Datei zu speichern. Sie können entweder den IANA-oder ISO-Zeichensatz Namen oder einen Punkt (.) gefolgt von einem 3 bis 5 stelligen Dezimaltrennzeichen-Code Page Bezeichner verwenden, um den zu verwendenden Zeichensatz anzugeben. Eine Liste der unterstützten Codepagebezeichner und Zeichensätze finden Sie unter [Code Page Identifiers (Codepagebezeichner)](/windows/win32/Intl/code-page-identifiers).

Standardmäßig sucht Visual Studio nach einer Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in einem Unicode-Format codiert ist, z. B. UTF-16 oder UTF-8. Wenn keine Byte Reihenfolge Markierung gefunden wird, wird davon ausgegangen, dass die Quelldatei mithilfe der aktuellen Benutzer Codepage codiert wird, es sei denn, Sie geben mithilfe der **"/Source-charset"** -Option einen Zeichensatz Namen oder eine Codepage an. Visual Studio lässt zu, dass Sie Ihren C++-Quellcode mithilfe verschiedener Zeichencodierungen speichern. Weitere Informationen zu Quell-und Ausführungs Zeichensätzen finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Sprachdokumentation.

Der Quell Zeichensatz, den Sie angeben, muss die 7-Bit-ASCII-Zeichen denselben Code Punkten in Ihrem Zeichensatz zuordnen, oder es werden wahrscheinlich viele Kompilierungsfehler befolgt. Der Quell Zeichensatz muss auch dem erweiterten Unicode-Zeichensatz zugewiesen werden können, der von UTF-8 Codierbar ist. Zeichen, die nicht in UTF-8 Codierbar sind, werden durch einen Implementierungs spezifischen Ersatz dargestellt. Der Microsoft-Compiler verwendet ein Fragezeichen für diese Zeichen.

Wenn Sie den Quell Zeichensatz und den Ausführungs Zeichensatz auf UTF-8 festlegen möchten, können Sie die **"/UTF-8"** -Compileroption als Verknüpfung verwenden. Diese Option ist äquivalent zu **/source-Charset:utf-8 und /execution-Charset:utf-8** in der Befehlszeile. Jede dieser Optionen aktiviert automatisch auch **/Validate-CharSet**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Erweitern Sie den Ordner **Konfigurations Eigenschaften**, **CC++/** und **Befehlszeile** .

1. Fügen Sie unter **zusätzliche Optionen**die Option **"/Source-charset"** hinzu, und geben Sie Ihre bevorzugte Codierung an.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
["/Execution-charset" (Ausführungs Zeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
