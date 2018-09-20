---
title: '-FU (Name Forced #using using-Datei) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs:
- C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e804aa48752d1f100e4c843fae9c0d5c70ae8b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423157"
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