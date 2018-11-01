---
title: Grundlagen benutzerdefinierter Buildschritte und Buildereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6522eb88eb282a1a3803e180e53027591f79374a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443890"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Grundlagen benutzerdefinierter Buildschritte und Buildereignisse

Innerhalb der Visual C++-Entwicklungsumgebung gibt es drei grundlegende Möglichkeiten, den Buildprozess anzupassen:

- **Benutzerdefinierte Buildschritte**

   Ein benutzerdefinierter Buildschritt ist eine Buildregel, die einem Projekt zugeordnet ist. Ein benutzerdefinierter Buildschritt kann eine auszuführende Befehlszeile, alle zusätzlichen Eingabe- oder Ausgabedateien und eine anzuzeigende Meldung angeben. Weitere Informationen finden Sie unter [How to: Add a Custom Build Step to MSBuild Projects (Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten)](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).

- **Benutzerdefinierte Buildtools**

   Ein benutzerdefiniertes Buildtool ist eine Buildregel, die mindestens einer Datei zugeordnet ist. Ein benutzerdefinierter Buildschritt kann Eingabedateien an ein benutzerdefiniertes Buildtool übergeben, was zu mindestens einer Ausgabedatei führt. Zum Beispiel werden die Hilfedateien in einer MFC-Anwendung mit einem benutzerdefinierten Buildtool erstellt. Weitere Informationen finden Sie unter [How to: Add Custom Build Tools to MSBuild Projects (Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten)](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) und [Specifying Custom Build Tools (Angeben von benutzerdefinierten Buildtools)](../ide/specifying-custom-build-tools.md).

- **Buildereignisse**

   Mit Buildereignissen können Sie das Build eines Projekts anpassen. Es gibt drei Buildereignisse: *Präbuild*, *Prälink* und *Postbuild*. Mit einem Buildereignis können Sie festlegen, dass eine Aktion zu einem bestimmten Zeitpunkt des Buildprozesses auftritt. Zum Beispiel können Sie ein Buildereignis dazu verwenden, eine Datei mit **regsvr32.exe** zu registrieren, nachdem das Projekt den Buildprozess abschließt. Weitere Informationen finden Sie unter [Specifying Build Events (Angeben von Buildereignissen)](../ide/specifying-build-events.md).

Die [Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md) können Ihnen dabei helfen, sicherzustellen, dass Ihre benutzerdefinierten Buildschritte und Buildereignisse ordnungsgemäß ausgeführt werden.

Das Ausgabeformat eines benutzerdefinierten Buildschritts oder Buildereignisses kann auch die Verwendbarkeit des Tools verbessern. Weitere Informationen finden Sie unter [Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).

Buildereignisse und benutzerdefinierte Buildschritte werden zusammen mit anderen Buildschritten in der folgenden Reihenfolge ausgeführt:

1. Präbuildereignis

2. Benutzerdefinierte Buildtools für individuelle Dateien

3. MIDL

4. Ressourcencompiler

5. Der C/C++-Compiler

6. Prälinkereignis

7. Linker oder Bibliothekar (nach Bedarf)

8. Manifesttool

9. BSCMake

10. Benutzerdefinierter Buildschritt für das Projekt

11. Postbuildereignis

`custom build step on the project` und `post-build event` werden sequenziell nach dem Abschluss aller anderen Buildprozesse ausgeführt.

## <a name="see-also"></a>Siehe auch

[Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)<br>
[Gängige Makros für Buildbefehle und -eigenschaften.](../ide/common-macros-for-build-commands-and-properties.md)
