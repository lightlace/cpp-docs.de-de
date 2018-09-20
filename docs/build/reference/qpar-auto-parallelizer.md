---
title: -Qpar (automatische Parallelisierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e69bc999721bf833f100418442315fc8bb69e6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413899"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (Automatische Parallelisierung)

Ermöglicht die [Auto-Parallelisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) Funktion des Compilers, Schleifen in Ihrem Code automatisch zu parallelisieren.

## <a name="syntax"></a>Syntax

```
/Qpar
```

## <a name="remarks"></a>Hinweise

Wenn der Compiler automatisch Schleifen im Code parallelisiert, verteilt er über mehrere Prozessorkerne Berechnung. Eine Schleife ist parallelisiert, nur dann, wenn der Compiler bestimmt, dass es zulässig ist, dazu, und diese Parallelisierung Leistung verbessert.

Die `#pragma loop()` Direktiven sind verfügbar, mit denen den Optimierer bestimmte Schleifen zu parallelisieren. Weitere Informationen finden Sie unter [Schleife](../../preprocessor/loop.md).

Informationen zum Aktivieren von ausgehenden Nachrichten für den Auto-parallelisierer finden Sie unter [/qpar-Report (Auto-Parallelizer-Berichtsebene)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>So legen Sie die /Qpar-Compileroption in Visual Studio fest

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

1. In der **Eigenschaftenseiten** Dialogfeld **C/C++-** Option **Befehlszeile**.

1. In der **zusätzliche Optionen** geben `/Qpar`.

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>So legen Sie die /Qpar Compileroption programmgesteuert fest

- Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)<br/>
[/Qpar-report (Berichtebene der automatischen Parallelisierung)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[Parallele Programmierung in systemeigenem Code](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)