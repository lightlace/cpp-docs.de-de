---
title: /homeparams (Registerparameter in den Stapel kopieren)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: a1f9269c7deae6c9ae2e4f198006ad09dd37abc3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820662"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Registerparameter in den Stapel kopieren)

Erzwingt, dass in Registern übergebene Parameter auch an ihre Positionen im Stapel Funktionseinstieg geschrieben werden.

## <a name="syntax"></a>Syntax

> **/homeparams**

## <a name="remarks"></a>Hinweise

Diese Compileroption ist nur verfügbar, in die systemeigene und Cross-Compiler, die X64 abzielen.

Die Aufrufkonvention X64 erfordert Stack Speicherplatz für alle Parameter, auch für Parameter, die in Registern übergeben werden. Weitere Informationen finden Sie unter [Parameterübergabe](../../build/x64-calling-convention.md#parameter-passing). Standardmäßig werden nicht die Registerparameter in den Stapelspeicherplatz dafür in Releasebuilds kopiert. Dies erschwert es zum Debuggen einer optimierten Releasebuild des Programms.

Für Releasebuilds, können Sie die **/homeparams in den** Option aus, um den Compiler an, kopieren Sie erzwingen, dass registrieren Parameter für den Stapel, um sicherzustellen, dass Sie Ihre Anwendung debuggen können. **/ homeparams in den** einer verminderten Leistung, da es sich um einen zusätzlichen Zyklus der Registerparameter in den Stapel laden erfordert.

In Debugbuilds wird der Stapel immer mit Parametern in Registern übergeben aufgefüllt.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Öffnen der **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
