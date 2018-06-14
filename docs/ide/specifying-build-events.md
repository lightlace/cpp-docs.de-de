---
title: Angeben von Buildereignissen | Microsoft-Dokumentation
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334963"
---
# <a name="specifying-build-events"></a>Angeben von Buildereignissen

Sie können Buildereignisse verwenden, um Befehle festzulegen, die vor dem Verknüpfungsvorgang oder nach Beenden des Builds ausgeführt werden.

Buildereignisse werden nur ausgeführt, wenn der Build die betreffenden Punkte im Buildprozess erfolgreich erreicht. Wenn ein Fehler im Build auftritt, findet das *Postbuildereignis* nicht statt. Wenn der Fehler vor der Verknüpfungsphase auftritt, finden weder das *Prälink-* noch das *Postbuildereignis* statt. Darüber hinaus findet das *Prälinkereignis* nicht statt, wenn keine Dateien verknüpft werden müssen. Das *Prälinkereignis* ist ebenfalls nicht in Projekten verfügbar, die keinen Verknüpfungsschritt enthalten.

Wenn keine Dateien erstellt werden müssen, finden keine Buildereignisse statt.

Allgemeine Informationen zu Buildereignissen finden Sie unter [Understanding Custom Build Steps and Build Events (Grundlagen benutzerdefinierter Buildschritte und Buildereignisse)](../ide/understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Angeben eines Buildereignisses

1. Klicken Sie im **Projektmappen-Explorer** auf das Projekt, für das Sie das Buildereignis angeben möchten.

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

1. Wählen Sie im Ordner **Buildereignisse** eine Buildereignis-Eigenschaftenseite aus.

1. Geben Sie die Eigenschaften an, die zu dem Buildereignis gehören:

   - Geben Sie in der **Befehlszeile** einen Befehl so ein, wie Sie ihn über die Eingabeaufforderung eingeben würden. Geben Sie einen gültigen Befehl oder eine Batchdatei sowie alle erforderlichen Ein- und Ausgabedateien an. Geben Sie den Batchbefehl **call** vor dem Namen einer Batchdatei an, um sicherzustellen, dass alle nachfolgenden Befehle ausgeführt werden.

      Mehrere Ein- und Ausgabedateien können symbolisch mit MSBuild-Makros angegeben werden. Weitere Informationen zum Angeben des Speicherorts von Dateien oder der Namen von mehreren Dateien finden Sie unter [Common Macros for Build Commands and Properties (Gängige Makros für Buildbefehle und -eigenschaften)](../ide/common-macros-for-build-commands-and-properties.md).

      Da das Zeichen „%“ von MSBuild reserviert ist, ersetzen Sie jedes **%**-Escapezeichen durch die Escapesequenz für Hexadezimalzahlen **%25**, wenn Sie eine Umgebungsvariable angeben. Ersetzen Sie beispielsweise **%WINDIR%** durch **%25WINDIR%25**. MSBuild ersetzt jede **%25**-Sequenz mit dem **%**-Zeichen, bevor auf die Umgebungsvariablen zugegriffen wird.

   - Geben Sie unter **Beschreibung** für dieses Ereignis eine Beschreibung ein. Wenn dieses Ereignis auftritt, wird die Beschreibung im **Ausgabefenster** ausgegeben.

   - Geben Sie für **vom Build ausgeschlossen** **Ja** an, wenn das Ereignis nicht ausgeführt werden soll.

## <a name="see-also"></a>Siehe auch

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)  
[Gängige Makros für Buildbefehle und -eigenschaften.](../ide/common-macros-for-build-commands-and-properties.md)  
[Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md)  
