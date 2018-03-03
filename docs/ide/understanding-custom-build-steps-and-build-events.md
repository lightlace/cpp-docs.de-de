---
title: Benutzerdefinierte Buildschritte und Buildereignisse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9abb7ff0b9a39656999e7a53b476056f7a5b1558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Grundlagen benutzerdefinierter Buildschritte und Buildereignisse
Von in der Visual C++-Entwicklungsumgebung gibt es drei grundlegende Methoden zum Anpassen des Buildprozesses:  
  
 **Benutzerdefinierte Buildschritte**  
 Ein benutzerdefinierter Buildschritt ist eine Buildregel einem Projekt zugeordnet. Ein benutzerdefinierten Buildschritt kann über die Befehlszeile ausgeführt wird, eine zusätzliche Eingabe oder Ausgabedateien und eine anzuzeigende Meldung angeben. Weitere Informationen finden Sie unter [wie: Hinzufügen einer benutzerdefinierten Buildschritt zu MSBuild-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Benutzerdefinierte Buildtools**  
 Ein benutzerdefiniertes Buildtool ist eine Buildregel, die eine oder mehrere Dateien zugeordnet. Ein benutzerdefinierten Buildschritt kann Eingabedateien übergeben, um ein benutzerdefiniertes Buildtool, was in einem führt ein oder mehrere Ausgabedateien. Beispielsweise werden die Hilfedateien in einer MFC_Anwendung mit der ein benutzerdefiniertes Buildtool erstellt. Weitere Informationen finden Sie unter [wie: Hinzufügen benutzerdefinierter Buildtools zu MSBuild-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) und [angeben von benutzerdefinierten Buildtools](../ide/specifying-custom-build-tools.md).  
  
 **Buildereignisse**  
 Buildereignisse können Sie ein Projekt anpassen. Es gibt drei Buildereignisse: *Präbuild*, *Linkervorstufen*, und *Postbuild*. Ein Buildereignis können Sie eine Aktion aus, um zu einem bestimmten Zeitpunkt während des Buildvorgangs auftreten angeben. Beispielsweise können Sie eine Buildereignis registrieren Sie eine Datei mit **regsvr32.exe** nach Abschluss des Projekts erstellen. Weitere Informationen finden Sie unter [Festlegen von Buildereignissen](../ide/specifying-build-events.md).  
  
 [Problembehandlung bei Anpassungen erstellen](../ide/troubleshooting-build-customizations.md) können Sie sicherstellen, dass Ihre benutzerdefinierte Buildschritte und Buildereignisse wie erwartet ausgeführt werden.  
  
 Das Ausgabeformat eines benutzerdefinierten Buildschritts oder Buildereignisses kann auch die Verwendbarkeit des Tools verbessern. Weitere Informationen finden Sie unter [Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Buildereignisse und benutzerdefinierte Buildschritte, führen Sie in der folgenden Reihenfolge zusammen mit anderen Buildschritte:  
  
1.  Präbuildereignis  
  
2.  Benutzerdefinierte Buildtools für einzelne Dateien  
  
3.  MIDL  
  
4.  Ressourcencompiler  
  
5.  C/C++-compiler  
  
6.  Prälinkereignis  
  
7.  Linker oder Bibliothekar (nach Bedarf)  
  
8.  Manifesttool  
  
9. BSCMake  
  
10. Benutzerdefinierter Buildschritt für das Projekt  
  
11. Postbuildereignis  
  
 Die `custom build step on the project` und ein `post-build event` ausführen, sequenziell nach dem Erstellen aller anderen Prozesse Fertig stellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)   
 [Allgemeine Makros für Buildbefehle und-Eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)   
 [Dialogfeld "Texttool Build-Reihenfolge"](http://msdn.microsoft.com/en-us/6204c5b1-7ce9-4948-9ff6-0268642ee14c)