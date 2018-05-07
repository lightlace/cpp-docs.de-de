---
title: Festlegen von Buildereignissen | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs:
- C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5940f0d6efaec402a4a85ed659f42d7eab1bf91d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-build-events"></a>Angeben von Buildereignissen

Buildereignisse können Sie Befehle angeben, die ausgeführt wird, bevor der Build gestartet wird, bevor Sie den Verknüpfungsvorgang oder nachdem der Build abgeschlossen ist.

Buildereignisse werden nur ausgeführt, wenn der Build die betreffenden Punkte im Buildprozess erfolgreich erreicht. Bei einem in den Build Fehler der *Postbuild* Ereignis tritt nicht auf, wenn der Fehler weder vor der verknüpfungsframework-Phase tritt auf der *Linkervorstufen* noch die *Postbuild* Ereignis Tritt auf. Darüber hinaus, wenn keine Dateien verknüpft werden, müssen die *Linkervorstufen* Ereignis tritt nicht auf. Die *Linkervorstufen* Ereignis ist auch nicht verfügbar in Projekten, die einen Linkschritt nicht enthalten.

Wenn keine Dateien erstellt werden müssen, treten keine Buildereignisse.

Allgemeine Informationen zu Buildereignissen finden Sie unter [benutzerdefinierte Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Angeben eines Buildereignisses

1. Klicken Sie im **Projektmappen-Explorer** auf das Projekt, für das Sie das Buildereignis angeben möchten.

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).

1. In der **Buildereignisse** Ordner, wählen Sie eine Ereignis-Eigenschaftsseite "Build".

1. Geben Sie das Buildereignis zugeordneten Eigenschaften:

   - In **Befehlszeile**, geben Sie einen Befehl aus, als ob Sie sie an der Eingabeaufforderung angegeben wurden. Geben Sie einen gültigen Befehl oder eine Batchdatei, und alle erforderlichen Eingabe- oder Ausgabedateien. Geben Sie die **Aufrufen** batch-Befehl vor dem Namen einer Batchdatei aus, um zu gewährleisten, dass alle nachfolgenden Befehle ausgeführt werden.

      Mehrere Eingabe- und Dateien können symbolisch mit MSBuild-Makros angegeben werden. Informationen zum Angeben von den Speicherort der Dateien oder die Namen von Sätzen von Dateien finden Sie unter [allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md).

      Da das Zeichen "%" von MSBuild reserviert ist, wenn Sie angeben, eine Umgebungsvariable ersetzen Sie jeden **%** escape-Zeichen mit der **% 25** hexadezimale Escapesequenz. Ersetzen Sie z. B. **"% windir%"** mit **25WINDIR % 25**. MSBuild ersetzt jede **% 25** Sequenz mit dem **%** Zeichen, bevor er die Umgebungsvariable zugreift.

   - In **Beschreibung**, geben Sie eine Beschreibung für dieses Ereignis. Die Beschreibung wird ausgegeben, um die **Ausgabe** Fenster, wenn dieses Ereignis auftritt.

   - In **vom Build ausgeschlossen**, geben Sie **Ja** , wenn Sie nicht, dass das Ereignis ausgeführt möchten.

## <a name="see-also"></a>Siehe auch

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)  
[Gängige Makros für Buildbefehle und -eigenschaften.](../ide/common-macros-for-build-commands-and-properties.md)  
[Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md)  
