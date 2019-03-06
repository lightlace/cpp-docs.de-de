---
title: /FR, /Fr (SBR-Datei erstellen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
ms.openlocfilehash: 41b415889465441b0c53f12ec7f4aa412a636562
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418084"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (SBR-Datei erstellen)

Erstellt SBR-Dateien.

## <a name="syntax"></a>Syntax

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Hinweise

Beim Erstellungsvorgang erstellt das Microsoft Browse Information Maintenance-Hilfsprogramm (BSCMAKE) anhand dieser Dateien eine BSC-Datei, die zur Darstellung von Browseinformationen verwendet wird.

Mit **/FR** wird eine SBR-Datei mit vollständigen symbolischen Informationen erstellt.

Mit **/Fr** wird eine SBR-Datei ohne Informationen über lokale Variablen erstellt.

Wenn Sie keinen Wert für `filename`angeben, erhält die SBR-Datei denselben Basisnamen wie die Quelldatei.

**/Fr** ist veraltet. Verwenden Sie stattdessen **/FR** . Weitere Informationen hierzu finden Sie unter „Veraltete und entfernte Compileroptionen“ in [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

> [!NOTE]
>  Ändern Sie nicht die Erweiterung SBR. BSCMAKE erfordert, dass die Zwischendateien diese Erweiterung haben.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich die Eigenschaftenseite **C/C++**, **Browseinformationsdatei** aus.

1. Ändern Sie die Eigenschaft **Browseinformationsdatei** oder **Durchsuchen der Informationen aktivieren** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/F) Optionen](../../build/reference/output-file-f-options.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)
