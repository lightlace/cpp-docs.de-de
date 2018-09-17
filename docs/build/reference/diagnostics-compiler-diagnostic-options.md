---
title: -Diagnose (Diagnose-Compileroptionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs:
- C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97b5e3ef2e5c14ae93d4fcc3b016f4dbc955edbd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709162"
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

2. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **allgemeine** Eigenschaftenseite.

3. Verwenden Sie das Dropdown-Steuerelement in der **Diagnoseformat** Feld Wählen Sie eine Diagnose Anzeigeoption. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)