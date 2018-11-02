---
title: '/FU (Name der expliziten #using-Datei)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: ecd9290336cfd6efd183bdd701f1d447b7ddaf2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492091"
---
# <a name="fu-name-forced-using-file"></a>/FU (Name der expliziten #using-Datei)

Eine Compileroption, mit denen Sie als Alternative zum Übergeben eines Dateinamens zum [#using-Direktive](../../preprocessor/hash-using-directive-cpp.md) im Quellcode.

## <a name="syntax"></a>Syntax

> **/ FU** *Datei*

## <a name="arguments"></a>Argumente

*datei*<br/>
Gibt die Metadatendatei, die in diesem Kompilierungsvorgang verwiesen.

## <a name="remarks"></a>Hinweise

Der Schalter/fu dauert nur einen Dateinamen an. Um mehrere Dateien anzugeben, verwenden Sie/fu mit jeweils ein.

Wenn Sie C++ verwenden c++ / CLI und verweisen auf Metadaten mit den [Friend-Assemblys](../../dotnet/friend-assemblies-cpp.md) Funktion können keine **/FU**. Sie müssen die Metadaten im Code mithilfe von verweisen `#using`– zusammen mit den `[as friend]` Attribut. Friend-Assemblys werden nicht unterstützt, in Visual C++-komponentenerweiterungen C++ / CX.

Informationen dazu, wie Sie eine Assembly oder ein Modul für die common Language Runtime (CLR) zu erstellen, finden Sie unter [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md). Informationen zur Verwendung für die Erstellung in C++ / CX, finden Sie unter [Erstellen von apps und Bibliotheken](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **erweitert** Eigenschaftenseite.

1. Ändern der **erzwungene #using using** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)