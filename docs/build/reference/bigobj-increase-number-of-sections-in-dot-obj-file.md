---
title: /bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 30c02c72496e3bb91da3b39e1870f1dc5a2c040a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493110"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)

**/bigobj** vergrößert die Anzahl der Abschnitte, die eine Objektdatei enthalten kann.

## <a name="syntax"></a>Syntax

> **/bigobj**

## <a name="remarks"></a>Hinweise

Standardmäßig kann eine Objektdatei bis zu 65.279 (fast 2 ^ 16) adressierbare Abschnitte enthalten. Dieser Grenzwert gilt unabhängig davon, welche Zielplattform angegeben wird. **/bigobj** erhöht die adresskapazität auf 4.294.967.296 (2 ^ 32).

Die meisten Module generieren nie eine OBJ-Datei, die mehr als 65.279 Abschnitte enthält. Computergenerierter Code oder Code, der Vorlagen Bibliotheken stark nutzt, erfordert möglicherweise OBJ-Dateien, die mehr Abschnitte enthalten können. **/bigobj** ist für universelle Windows-Plattform-Projekte (UWP) standardmäßig aktiviert, da der vom computergenerierte XAML-Code eine große Anzahl von Headern enthält. Wenn Sie diese Option in einem UWP-App-Projekt deaktivieren, generiert der Code möglicherweise Compilerfehler C1128.

Weitere Informationen zum PE-COFF-Objektdatei Format finden Sie im [PE-Format](/windows/win32/debug/pe-format) in der Windows-Dokumentation.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Geben Sie die **/bigobj** -Compileroption im Feld **zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
