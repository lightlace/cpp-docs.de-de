---
title: /Gm (Minimale Neuerstellung aktivieren)
ms.date: 11/12/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 4a66dda37b84119a4b8bc23f7fc719d50e8786f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292067"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (Minimale Neuerstellung aktivieren)

Veraltet. Aktiviert die minimale Neuerstellung, die bestimmt, ob C++-Quelldateien, die geänderte C++-Klassendefinitionen enthalten (gespeichert in Headerdateien (.h)) neu kompiliert werden müssen.

## <a name="syntax"></a>Syntax

```
/Gm
```

## <a name="remarks"></a>Hinweise

**/ GM** ist veraltet. Ein Build für bestimmte Arten von Änderungen der Header möglicherweise nicht ausgelöst. Sie können diese Option sicher aus Projekten entfernen. Um Entwicklungszeiten zu verbessern, empfiehlt es sich um Verwendung vorkompilierter Header und inkrementelle und parallele Buildoptionen stattdessen. Eine Liste der Ersetzte Compileroptionen, finden Sie unter den **veraltete und entfernte Compileroptionen** im Abschnitt [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

Der Compiler speichert Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen während der ersten Kompilierung in der .idb-Datei des Projekts. (Abhängigkeitsinformationen Teilen mit der Quelldatei von welcher Klassendefinition abhängt und welcher .h-Datei die Definition befindet sich im.) Nachfolgende Kompilierungen verwenden die in der .idb-Datei gespeicherte Informationen um zu bestimmen, ob eine Quelldatei kompiliert werden muss, auch wenn es sich um eine geänderte .h-Datei enthält.

> [!NOTE]
> Die minimale Neuerstellung basiert auf Klassendefinitionen, die sich zwischen Includedateien nicht ändern. Klassendefinitionen müssen für ein Projekt global sein (es sollte nur eine Definition für eine bestimmte Klasse vorhanden sein), da die Abhängigkeitsinformationen in der .idb-Datei für das gesamte Projekt erstellt werden. Wenn Sie mehr als eine Definition für eine Klasse in Ihrem Projekt haben, deaktivieren Sie die minimale Neuerstellung.

Da der incremental Linker die Windows-Metadaten in OBJ-Dateien enthalten sind, mithilfe von nicht unterstützt. die [/ZW (Windows-Runtime-Kompilierung)](zw-windows-runtime-compilation.md) -Option der **/GM** inkompatibel mit  **/ ZW**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **minimale Neuerstellung aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
