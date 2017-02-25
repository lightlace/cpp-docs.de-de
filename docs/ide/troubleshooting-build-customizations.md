---
title: "Problembehandlung f&#252;r Buildanpassungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildereignisse [C++], Problembehandlung"
  - "Buildschritte [C++], Problembehandlung"
  - "Builds [C++], Buildereignisse"
  - "Builds [C++], Problembehandlung"
  - "Benutzerdefinierte Buildschritte [C++], Problembehandlung"
  - "Ereignisse [C++], Build"
  - "Problembehandlung [C++], Builds"
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Problembehandlung f&#252;r Buildanpassungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn benutzerdefinierte Buildschritte und Buildereignisse nicht erwartungsgemäß ausgeführt werden, können Sie auf verschiedene Weisen überprüfen, wo der Fehler liegt.  
  
-   Stellen Sie sicher, dass die durch benutzerdefinierte Buildschritte generierten Dateien mit den Dateien übereinstimmen, die Sie als Ausgaben deklarieren.  
  
-   Wenn durch benutzerdefinierte Buildschritte Dateien generiert werden, die Eingaben oder Abhängigkeiten anderer \(benutzerdefinierter oder sonstiger\) Buildschritte darstellen, sollten Sie sicherstellen, dass diese Dateien dem Projekt hinzugefügt werden.  Und stellen Sie sicher, dass die Tools, die diese Dateien nutzen, nach dem benutzerdefinierten Buildschritt ausgeführt werden.  
  
-   Fügen Sie `@echo on` als ersten Befehl hinzu, um anzuzeigen, welche Aktion vom benutzerdefinierten Buildschritt gerade ausgeführt wird.  Die Buildereignisse und die Buildschritte werden in einer temporären BAT\-Datei gespeichert und ausgeführt, wenn das Projekt erstellt wird.  Daher können Sie dem Buildereignis oder den Buildschrittbefehlen eine Fehlerüberprüfung hinzufügen.  
  
-   Überprüfen Sie das Buildprotokoll im Verzeichnis für Zwischendateien, um festzustellen, welche Aktion ausgeführt wird.  Der Pfad und der Name des Buildprotokolls werden vom **MSBuild**\-Makroausdruck, **$\(IntDir\)\\$\(MSBuildProjectName\).log** dargestellt.  
  
-   Ändern Sie die Projekteinstellungen, um zusätzliche Informationen im Buildprotokoll zu sammeln.  Klicken Sie im Menü **Extras** auf **Optionen**.  Erweitern Sie im Dialogfeld **Optionen** den Knoten **Projekte und Projektmappen**, und klicken Sie anschließend auf den Knoten **Erstellen und Ausführen**.  Klicken Sie dann im Feld **Ausführlichkeit der Protokolldatei des MSBuild\-Projektbuilds** auf **Detailliert**.  
  
-   Überprüfen Sie die Werte eventuell verwendeter Dateinamen\- oder Verzeichnismakros.  Der echo\-Befehl kann für einzelne Makros ausgeführt, oder `copy %0 command.bat` kann am Anfang des benutzerdefinierten Buildschritts hinzugefügt werden. Dadurch werden die Befehle des benutzerdefinierten Buildschritts in die Datei command.bat kopiert, wobei alle Makros erweitert sind.  
  
-   Führen Sie benutzerdefinierte Buildschritte und Buildereignisse einzeln aus, um ihr Verhalten zu überprüfen.  
  
## Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)