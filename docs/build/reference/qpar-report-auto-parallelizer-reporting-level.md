---
title: /Qpar-report (Auto-Parallelizer-Berichtsebene)
ms.date: 11/04/2016
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
ms.openlocfilehash: 4ab14f890d888664b2847f3e3d4b193d7c77da1a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419906"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (Auto-Parallelizer-Berichtsebene)

Ermöglicht die Berichtsfunktion des Compilers [Auto-Parallelisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) und gibt die Ebene der informationsmeldungen für die Ausgabe während der Kompilierung.

## <a name="syntax"></a>Syntax

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>Hinweise

**/Qpar-report:1**<br/>
Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden.

**/Qpar-report:2**<br/>
Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden und auch für Schleifen, die nicht, zusammen mit einen Ursachencode parallel ausgeführt werden.

Nachrichten werden an Stdout gesendet. Wenn keine Informationsmeldungen angezeigt werden, enthält der Code keine Schleifen oder die Berichterstellungsebene wurde nicht festgelegt, um Bericht-Schleifen, die nicht parallel ausgeführt werden, zu melden. Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>So legen Sie die /Qpar-report-Compileroption in Visual Studio fest

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

1. In der **Eigenschaftenseiten** Dialogfeld **C/C++-** Option **Befehlszeile**.

1. In der **zusätzliche Optionen** geben `/Qpar-report:1` oder `/Qpar-report:2`.

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>So legen Sie die Compileroption "/Qpar-report" programmgesteuert fest

- Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Parallele Programmierung in systemeigenem Code](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
