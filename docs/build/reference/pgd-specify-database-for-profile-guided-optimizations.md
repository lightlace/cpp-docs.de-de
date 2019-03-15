---
title: /PGD (Angeben einer Datenbank für die profilgesteuerte Optimierungen)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: e1d7c9fcb94a9351ce94b66e04b4bfc523248f4e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812199"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Angeben einer Datenbank für die profilgesteuerte Optimierungen)

**Die/PGD-Option ist veraltet.** Ab Visual Studio 2015, bevorzugen die [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) stattdessen Optionen des Linkers. Diese Option wird verwendet, um den Namen der PGD-Datei verwendet wird, durch den Prozess für die profilgesteuerte Optimierung anzugeben.

## <a name="syntax"></a>Syntax

> **/PGD:**_filename_

## <a name="argument"></a>Argument

*filename*<br/>
Gibt den Namen der PGD-Datei, die zum Speichern von Informationen zum ausgeführten Programm verwendet wird.

## <a name="remarks"></a>Hinweise

Wenn es sich bei den veralteten [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) option können Sie **/PGD** einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei an. Wenn Sie keinen angeben **/PGD**, der Basisnamen für die PGD-Datei ist der Name der Ausgabedatei (.exe oder .dll) Basis identisch und wird im gleichen Verzeichnis aus dem auf der Link aufgerufen wurde erstellt.

Wenn es sich bei den veralteten **/LTCG: PGOPTIMIZE** option können Sie die **/PGD** Option aus, um den Namen der PGD-Datei verwenden Sie zum Erstellen des optimierten Images angeben. Die *Filename* Argument sollte übereinstimmen. die *Filename* angegebenen **/LTCG: PGINSTRUMENT**.

Weitere Informationen finden Sie unter [Profile-Guided Optimizations](../profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. Ändern der **Profilgesteuerte Datenbank** Eigenschaft. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
