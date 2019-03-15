---
title: /Qvec-report (Auto-Vectorizer-Berichtsebene)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 655be3581eee4b23a8d0f2bcfaea7d07c8b1b07c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815943"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Auto-Vectorizer-Berichtsebene)

Ermöglicht die Berichtsfunktion des Compilers [Auto-Vektorisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) und gibt die Ebene der informationsmeldungen für die Ausgabe während der Kompilierung.

## <a name="syntax"></a>Syntax

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>Hinweise

**/Qvec-report:1**<br/>
Gibt eine informationsmeldung für Schleifen an, die vektorisiert werden.

**/Qvec-report:2**<br/>
Gibt eine informationsmeldung für Schleifen an, die vektorisiert werden und für Schleifen an, die nicht, zusammen mit einen Ursachencode vektorisiert werden.

Weitere Informationen zu Ursachencodes und Meldungen, finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>So legen Sie die /Qvec-report-Compileroption in Visual Studio fest

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

1. In der **Eigenschaftenseiten** Dialogfeld **C/C++-** Option **Befehlszeile**.

1. In der **zusätzliche Optionen** geben `/Qvec-report:1` oder `/Qvec-report:2`.

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>So legen Sie die /Qvec-report Compileroption programmgesteuert fest

- Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[Parallele Programmierung in systemeigenem Code](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
