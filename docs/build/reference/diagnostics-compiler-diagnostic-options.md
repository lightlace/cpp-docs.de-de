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
ms.openlocfilehash: 6b7d043e00204fa191530f03bbed069d71a25fc5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822304"
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

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
