---
title: Problembehandlung für Buildanpassungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d48e9f7bdcbf422a25fb0bdb40411e6c662fadc2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33330271"
---
# <a name="troubleshooting-build-customizations"></a>Problembehandlung für Buildanpassungen
Wenn Ihre benutzerdefinierten Buildschritte oder -ereignisse sich nicht wie erwartet verhalten, gibt es mehrere Möglichkeiten, um herauszufinden, wo der Fehler liegt.  
  
-   Stellen Sie sicher, dass die Dateien, die Ihre benutzerdefinierten Buildschritte erstellen, mit den Dateien übereinstimmen, die Sie als Ausgaben deklarieren.  
  
-   Wenn Ihre Buildschritte Dateien generieren, die Eingaben oder Abhängigkeiten von anderen Buildschritten sind, stellen Sie sicher, dass diese Dateien Ihrem Projekt hinzugefügt werden. Stellen Sie außerdem sicher, dass die Tools, die diese Dateien verarbeiten, nach dem benutzerdefinierten Buildschritt ausgeführt werden.  
  
-   Fügen Sie `@echo on` als ersten Befehl ein, um anzuzeigen, was Ihr benutzerdefinierter Buildschritt tatsächlich durchführt. Die Buildereignisse und -schritte werden in eine temporäre BAT-Datei eingefügt und ausgeführt, wenn das Projekt erstellt wird. Aus diesem Grund können Sie Ihren Befehlen für das Buildereignis oder den Buildschritt eine Fehlerüberprüfung hinzufügen.  
  
-   Überprüfen Sie das Buildprotokoll im Zwischendateiverzeichnis, um zu sehen, was tatsächlich ausgeführt wurde. Der Pfad und Name des Buildprotokolls wird durch den **MSBuild**-Makroausdruck **$(IntDir)\\$(MSBuildProjectName).log** dargestellt.  
  
-   Ändern Sie die Projekteinstellungen, um mehr als die Standardmenge von Informationen im Buildprotokoll zu sammeln. Klicken Sie im Menü **Extras** auf **Optionen**. Klicken Sie im Dialogfeld **Optionen** auf den Knoten **Projekte und Projektmappen**, und klicken Sie dann auf den Knoten **Erstellen und Ausführen**. Klicken Sie dann im Feld **Ausführlichkeit der Protokolldatei des MSBuild-Projektbuilds** auf **Detailliert**.  
  
-   Überprüfen Sie die Werte der Dateinamen oder Verzeichnismakros, die Sie verwenden. Sie können Makros individuell abrufen oder dem Anfang Ihres benutzerdefinierten Buildschritts `copy %0 command.bat` hinzufügen, wodurch die Befehle Ihres benutzerdefinierten Buildschritts mit allen erweiterten Makros in „command.bat“ kopiert werden.  
  
-   Führen Sie benutzerdefinierte Buildschritte und Buildereignisse einzeln aus, um deren Verhalten zu überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)