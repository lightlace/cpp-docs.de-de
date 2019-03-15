---
title: /bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)
ms.date: 11/04/2016
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: a9685834fc3e1de246c9d9d60d206538b744ce3e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809859"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Erhöhen der Anzahl von Abschnitten in der OBJ-Datei)

**/ bigobj** erhöht die Anzahl von Abschnitten, die eine Objektdatei enthalten kann.

## <a name="syntax"></a>Syntax

```
/bigobj
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung kann eine Objektdatei bis zu 65.536 (2^16) adressierbare Abschnitte enthalten. Dabei spielt es keine Rolle, welche Zielplattform angegeben ist. **/ bigobj** erhöht diese Adressenkapazität auf 4.294.967.296 (2 ^ 32).

Von den meisten Modulen werden keine OBJ-Dateien erzeugt, die mehr als 65.536 Abschnitte enthalten. Für computergenerierten Code oder Code, in dem häufig Gebrauch von Vorlagenbibliotheken gemacht wird, sind allerdings unter Umständen OBJ-Dateien erforderlich, die mehr Abschnitte enthalten. **/ bigobj** ist standardmäßig für universelle Windows-Plattform (UWP) Projekte aktiviert, da der computergenerierte XAML-Code viele Header enthält. Wenn Sie diese Option auf das Projekt für eine UWP-app deaktivieren, werden Sie wahrscheinlich Compilerfehler C1128 auftritt.

Linker, die vor Visual C++ 2005 ausgeliefert können nicht gelesen werden OBJ-Dateien, die mit erzeugt wurden **/bigobj**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
