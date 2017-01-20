---
title: "Grundlagen benutzerdefinierter Buildschritte und Buildereignisse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildereignisse [C++], Reihenfolge von Ereignissen und Buildschritten"
  - "Buildschritte [C++]"
  - "Buildschritte [C++], Buildereignisse"
  - "Builds [C++], Benutzerdefinierte Buildschritte"
  - "Builds [C++], Ereignisse"
  - "Benutzerdefinierte Buildschritte [C++]"
  - "Benutzerdefinierte Buildschritte [C++], Anpassen von Builds"
  - "Ereignisse [C++], Build"
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Grundlagen benutzerdefinierter Buildschritte und Buildereignisse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aus der Visual C\+\+\-Entwicklungsumgebung heraus haben Sie drei grundlegende Möglichkeiten, um den Buildvorgang anzupassen:  
  
 **Benutzerdefinierte Buildschritte**  
 Ein benutzerdefinierter Buildschritt ist eine Buildregel, die einem Projekt zugeordnet ist.  In einem benutzerdefinierten Schritt können eine auszuführende Befehlszeile, beliebige zusätzliche Eingabe\- oder Ausgabedateien und eine anzuzeigende Meldung angegeben werden.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild\-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Benutzerdefinierte Buildtools**  
 Ein benutzerdefiniertes Buildtool ist eine mit mindestens einer Datei verknüpfte Buildregel.  Durch einen benutzerdefinierten Buildschritt können Eingabedateien an das benutzerdefinierte Buildtool übergeben werden, was mindestens eine Ausgabedatei ergibt.  Die Hilfedateien in einer MFC\-Anwendung werden beispielsweise anhand benutzerdefinierter Buildtools erstellt.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild\-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) und [Angeben von benutzerdefinierten Buildtools](../ide/specifying-custom-build-tools.md).  
  
 **Buildereignisse**  
 Buildereignisse ermöglichen Ihnen das Anpassen eines Projektbuilds.  Drei Buildereignisse sind verfügbar: *Präbuild*, *Prälink* und *Postbuild*.  Über ein Buildereignis können Sie eine Aktion angeben, die zu einer bestimmten Zeit im Buildvorgang ausgeführt wird.  Beispielweise können Sie über ein Buildereignis eine Datei mit **regsvr32.exe** registrieren, nachdem das Projektbuild abgeschlossen wurde.  Weitere Informationen finden Sie unter [Angeben von Buildereignissen](../ide/specifying-build-events.md).  
  
 Die [Problembehandlung für Buildanpassungen](../ide/troubleshooting-build-customizations.md) kann Sie dabei unterstützen, dass benutzerdefinierte Buildschritte und Buildereignisse erwartungsgemäß ausgeführt werden.  
  
 Das Ausgabeformat eines benutzerdefinierten Buildschritts oder Buildereignisses kann den Nutzen des Tools ebenfalls optimieren.  Weitere Informationen finden Sie unter [Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Buildereignisse und benutzerdefinierte Buildschritte werden zusammen mit anderen Buildschritten in der folgenden Reihenfolge ausgeführt:  
  
1.  Präbuildereignis  
  
2.  Benutzerdefinierte Buildtools für einzelne Dateien  
  
3.  MIDL  
  
4.  Ressourcencompiler  
  
5.  C\/C\+\+\-Compiler  
  
6.  Prälinkereignis  
  
7.  Linker oder Bibliothekar \(je nach Bedarf\)  
  
8.  Manifesttool  
  
9. BSCMake  
  
10. Benutzerdefinierter Buildschritt für das Projekt  
  
11. Postbuildereignis  
  
 Der `custom build step on the project` und ein `post-build event` werden sequentiell nach Abschluss aller anderen Buildprozesse ausgeführt.  
  
## Siehe auch  
 [Erstellen von C\+\+\-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)   
 [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)   
 [Tool Build Order Dialog Box](assetId:///6204c5b1-7ce9-4948-9ff6-0268642ee14c)