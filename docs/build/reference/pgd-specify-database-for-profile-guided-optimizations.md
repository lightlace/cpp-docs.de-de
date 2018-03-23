---
title: / PGD (Angeben einer Datenbank für Profilgesteuerte Optimierungen) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9947e95e3d6c96d07eb12eb2f2a579e0ea1b3a6a
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Angeben einer Datenbank für die profilgesteuerte Optimierungen)

**Die PGD-Option ist veraltet.** Ab Visual Studio 2015 bevorzugen die [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) Linkeroptionen stattdessen. Diese Option wird verwendet, um den Namen des vom Prozess Profilgesteuerte Optimierung verwendet die PGD-Datei angeben.

## <a name="syntax"></a>Syntax

> **/PGD:**_filename_

## <a name="argument"></a>Argument

*filename*<br/>
Gibt den Namen der PGD-Datei, die zum Speichern von Informationen zum ausgeführten Programm verwendet wird.

## <a name="remarks"></a>Hinweise

Bei den veralteten [/LTCG: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) mit **/PGD** einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei angeben. Wenn Sie keinen angeben **/PGD**, der Basisnamen für die PGD-Datei ist der Name der Ausgabedatei (.exe oder .dll) Basis identisch und wird im gleichen Verzeichnis, von dem die Verknüpfung aufgerufen wurde, erstellt.

Bei den veralteten **/LTCG: PGOPTIMIZE** aktivieren, verwenden Sie die **/PGD** Option aus, um den Namen der PGD-Datei zu verwenden, um das optimierte Image Erstellen angeben. Die *Filename* Argument übereinstimmen, die *Filename* angegebenen **/LTCG: PGINSTRUMENT**.

Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. Ändern der **Profilgesteuerte Datenbank** Eigenschaft. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)<br/>
