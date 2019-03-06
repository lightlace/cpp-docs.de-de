---
title: / Diagnostics (Diagnose-Compileroptionen)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: c8e9f2b6bc36d8a1dfdada00bca1c7a4dcf65256
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423260"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/ Diagnostics (Diagnose-Compileroptionen)

Verwenden der **/Diagnostics** -Compileroption verwenden, um die Anzeige der Informationen zum Fehler und Warnungen Speicherort angeben.

## <a name="syntax"></a>Syntax

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Hinweise

Diese Option wird in Visual Studio 2017 und höher unterstützt.

Die **/Diagnostics** -Compileroption steuert die Anzeige von Fehler- und Warnungsinformationen.

Die **/diagnostics:classic** ist die Standardoption, die nur die Nummer der Zeile meldet, in dem das Problem gefunden wurde.

Die **/diagnostics:column** Option umfasst auch die Spalte, in dem das Problem gefunden wurde. Damit können Sie identifizieren Sie die sprachspezifischen Konstrukt oder die Zeichen, das das Problem verursacht hat.

Die **/diagnostics:caret** Option enthält die Spalte, in dem das Problem gefunden wurde, und fügt ein Caretzeichen (^) unter den Speicherort in der Codezeile, in dem das Problem erkannt wurde.

Beachten Sie, dass in einigen Fällen der Compiler kein Problem erkennt, wo es aufgetreten ist. Ein fehlendes Semikolon kann z. B. nicht erkannt werden, bis Weitere, unerwartete Symbole aufgetreten sind. Die Spalte wird gemeldet, und die Einfügemarke befindet, in denen der Compiler hat festgestellt, dass etwas falsch ist, dies ist nicht immer war, in dem Sie Ihre Korrekturen vornehmen müssen.

Die **/Diagnostics** Option ist ab Visual Studio 2017 verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.

1. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **allgemeine** Eigenschaftenseite.

1. Verwenden Sie das Dropdown-Steuerelement in der **Diagnoseformat** Feld Wählen Sie eine Diagnose Anzeigeoption. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
