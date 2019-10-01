---
title: /LINKREPROTARGET (Name der Verknüpfungs Reproduktions Datei)
description: Die Option Linker oder Bibliotheks Tool, um einen Ziel Dateinamen für eine Link Reproduktion festzulegen.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPROTARGET
helpviewer_keywords:
- LINKREPROTARGET linker option
- /LINKREPROTARGET linker option
- -LINKREPROTARGET linker option
- linker repro reporting
ms.openlocfilehash: d629c4c2665239d03f38569677fa579b6c8d37e0
ms.sourcegitcommit: a361362354f6ce51eda4ffdb016b81c24cd225cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71712687"
---
# <a name="linkreprotarget-link-repro-file-name"></a>/LINKREPROTARGET (Name der Verknüpfungs Reproduktions Datei)

Weist den Linker oder das Bibliotheks Tool an, eine Link Reproduktion nur zu generieren, wenn das Ziel über den angegebenen Dateinamen verfügt.

## <a name="syntax"></a>Syntax

> **/LINKREPROTARGET:** _Dateiname_

### <a name="arguments"></a>Argumente

**/LINKREPROTARGET:** _File-Name_\
Der Ziel Dateiname, nach dem gefiltert werden soll. Eine Link Reproduktion wird nur generiert, wenn die benannte Datei das Ausgabeziel ist. Dateinamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden. Der Dateiname sollte den Basis Namen und die Erweiterung enthalten, jedoch nicht den Pfad.

## <a name="remarks"></a>Hinweise

Die Option **/LINKREPROTARGET** wird verwendet, um einen Ziel Dateinamen anzugeben, für den eine *Link* Reproduktion generiert werden soll. Eine Link Reproduktion ist ein Satz von buildartefakte, mit denen Microsoft ein Problem reproduzieren kann, das bei der Verknüpfungs Zeit oder bei Bibliotheks Vorgängen auftritt. Das linker-oder Bibliotheks Tool erzeugt eine Link Reproduktion, wenn Sie die [/LINKREPRO](linkrepro.md) -Option angeben, oder wenn Sie die Umgebungsvariable `link_repro` in Ihrer Befehlszeilen-Buildumgebung festlegen.

Die **/LINKREPROTARGET** -Option ist nützlich bei komplexen Builds, die den Linker oder das Bibliotheks Tool mehrmals aufrufen. Sie können ein bestimmtes Ziel für die Link Reproduktion angeben, z. b. " *Problem. dll*". Sie können die Link Reproduktion nur generieren, wenn das Tool eine bestimmte Datei erzeugt.

Weitere Informationen darüber, wie und wann eine Link Reproduktion erstellt werden muss, finden Sie im Abschnitt [Link](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) Reproduktionen ( [melden eines Problems mit dem C++ Microsoft-Toolset](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)).

Die Optionen **/LINKREPRO** und [/out](out-output-file-name.md) müssen festgelegt werden, damit die **/LINKREPROTARGET** -Option eine beliebige Auswirkung hat.

**/LINKREPROTARGET** ist ab Visual Studio 2019 Version 16,1 verfügbar.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **Linker** > **Befehlszeile** aus.

1. Geben Sie im Feld **zusätzliche Optionen** die Option **/LINKREPROTARGET:** _File-Name_ ein. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-linkerverweis](linking.md)\
[MSVC-Linkeroptionen](linker-options.md)\
[/LINKREPRO](linkrepro.md)
