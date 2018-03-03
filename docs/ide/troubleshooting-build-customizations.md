---
title: "Problembehandlung für Buildanpassungen | Microsoft Docs"
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
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fa3b2d3910a71d189f5177e13fbd91930e15ee8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="troubleshooting-build-customizations"></a>Problembehandlung für Buildanpassungen
Wenn Ihre benutzerdefinierte Buildschritte oder Ereignisse sind nicht wie erwartet verhält, gibt es mehrere Dinge, die Sie ausführen können, um herauszufinden, wo der Fehler ist.  
  
-   Stellen Sie sicher, dass die Dateien, die Ihre benutzerdefinierte Buildschritte Generieren der Dateien übereinstimmen, die Sie als Ausgaben deklarieren.  
  
-   Wenn Ihre benutzerdefinierte Buildschritte generieren alle Dateien, die Eingaben sind oder Abhängigkeiten von anderen Buildschritte (benutzerdefinierte oder anderweitig), stellen Sie sicher, dass diese Dateien zu Ihrem Projekt hinzugefügt werden. Und stellen Sie sicher, dass die Tools, die diese Dateien nutzen ausgeführt werden, nachdem das benutzerdefinierte Buildschritt.  
  
-   Fügen Sie zum Anzeigen Ihrer benutzerdefinierten Buildschritt tatsächlich ausgeführten `@echo on` als erster Befehl. Der Buildereignissen und Buildschritten sind in einer temporären bat-Datei abgelegt und ausgeführt werden, wenn das Projekt erstellt wird. Aus diesem Grund können Fehler beim Überprüfen der zu Ihrer Erstellung ein Ereignis hinzufügen oder Buildbefehle Schritt.  
  
-   Überprüfen Sie das Buildprotokoll im Verzeichnis temporären Dateien, um festzustellen, welche Aktion ausgeführt. Der Pfad und Name des Buildprotokolls wird dargestellt, indem die **MSBuild** Makro Expression, **$(IntDir)\\$(MSBuildProjectName) .log**.  
  
-   Ändern Sie die projekteinstellungen für mehr als die Standarddauer von Informationen im Buildprotokoll sammeln. Klicken Sie im Menü **Extras** auf **Optionen**. In der **Optionen** (Dialogfeld), klicken Sie auf die **Projekte und Projektmappen** Knoten, und klicken Sie dann auf die **erstellen und ausführen** Knoten. Klicken Sie auf die **Ausführlichkeit der Protokolldatei des MSBuild-Projekt Build** auf **detailliert**.  
  
-   Stellen Sie sicher, dass die Werte eines beliebigen oder Makros Datei, die Sie verwenden. Sie können Makros einzeln echo, oder Sie können hinzufügen `copy %0 command.bat` am Anfang der benutzerdefinierte Buildschritt, kopieren die vom benutzerdefinierten Buildschritt-Befehle Befehl mit erweiterten Makros.  
  
-   Führen Sie benutzerdefinierte Buildschritte und Buildereignisse einzeln, um ihr Verhalten zu überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)