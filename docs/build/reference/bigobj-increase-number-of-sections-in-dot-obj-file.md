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
ms.openlocfilehash: 46399dc0c1ff552b4fc963b686ac6aa6df8b6f71
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508714"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)

**/ bigobj** erhöht die Anzahl von Abschnitten, die eine Objektdatei enthalten kann.

## <a name="syntax"></a>Syntax

> **/bigobj**

## <a name="remarks"></a>Hinweise

Standardmäßig kann eine Objektdatei bis zu 65.279 enthalten (fast 2 ^ 16) adressierbare Abschnitte enthalten. Dieser Grenzwert gilt unabhängig davon, welchen Plattform angegeben ist. **/ bigobj** erhöht diese Adressenkapazität auf 4.294.967.296 (2 ^ 32).

Die meisten Module generiert nie eine .obj-Datei, die mehr als 65279 Abschnitte enthält. Allerdings kann vom Computer generierte Code oder Code, die intensiven Gebrauch von Vorlagenbibliotheken, macht OBJ-Dateien ist erforderlich, die mehr Abschnitte enthalten. **/ bigobj** ist standardmäßig für universelle Windows-Plattform (UWP) Projekte aktiviert, da der computergenerierte XAML-Code viele Header enthält. Wenn Sie diese Option auf das Projekt für eine UWP-app deaktivieren, kann Ihr Code Compilerfehler C1128 generieren.

Weitere Informationen zu der PE-COFF-Objektformat-Datei, finden Sie unter [PE-Format](/windows/desktop/debug/pe-format) in der Windows-Dokumentation.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/bigobj** -Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
